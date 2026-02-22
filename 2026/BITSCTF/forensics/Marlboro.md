# Marlboro

> "The smoke rises, carrying secrets within... Where there's smoke, there's fire..."
> We intercepted an encrypted transmission from a mysterious server. The data appears to be lost, but rumor has it some ancient legend is somewhere in this image.
> The original sender was obsessed with a programming language from hell itself - one where code mutates, logic inverts, and sanity is optional and insanity is permanence.

The challenge provided a file named `SaveMeFromThisHell.zip`. Initial analysis of the archive using `file`, `binwalk`, and `exiftool` revealed nothing suspicious. The ZIP metadata appeared clean and normal. After extracting the archive, a single image file was obtained: `Marlboro.jpg`.

Further inspection of `Marlboro.jpg` using `binwalk` revealed embedded files hidden within the image. The scan detected two additional files: `smoke.png` and `encrypted.bin`. To recover these files, `foremost` was used against the JPEG, successfully extracting both hidden artifacts for deeper analysis.

The file `smoke.png` was then examined using [Aperi'Solve](https://www.aperisolve.com/a17b0446c97023623c4cedf63d88b06a) to perform steganographic and metadata analysis. Within the EXIF metadata, a Base64-encoded string was discovered. After decoding it, the result pointed to the following URL:

```
https://zb3.me/malbolge-tools/
```

This strongly suggested that the challenge involved the Malbolge programming language  a notoriously complex and self-modifying esoteric language.

To continue the investigation, `zsteg` was run against `smoke.png`. This revealed embedded hidden text containing a decryption key and instructions:

```
# Marlboro Decryption Key
# Format: 32-byte XOR key in hexadecimal
KEY=c7027f5fdeb20dc7308ad4a6999a8a3e069cb5c8111d56904641cd344593b657
# Usage: XOR each byte of encrypted.bin with key[i % 32]
```

From this information, it was clear that `encrypted.bin` needed to be decrypted using a 32-byte repeating XOR key. Each byte of the encrypted file had to be XORed with the corresponding byte of the key, looping through the key using modulo indexing.

After performing the XOR decryption, the output revealed metadata indicating that the content was written in Malbolge:

```
Content-Type: text/x-malbolge
Interpreter: https://zb3.me/malbolge-tools/#interpreter
Language: Malbolge
```

This was followed by Malbolge source code:

```malbolge
D'`$##\!<5|jWVT/eRcONp_oJJHHF!3gfBc!?a_{)(xwYon4rqpi/mlkdibaf_%]ba`_XWVz=YRQPOsSRQ3ONGkKD,BAe(DCBA@?>7[5432V6v.3,P*).-&Jk)"!&}C#cy~wv<zyxZpotm3qSi/gOkd*KJ`ed]\"`Y^]\[TxRQVOTSLpPONMLEiIH*)?>bB$@987[Z:38765.Rsr*/.-&%$#G'~f$#z@~}|{t:[wvonm3kSonmlkdihg`&GFbaZ~^@VUTYRQPtNMLKPImGFKJCBf)E>bB;@?>7[5432Vw/43,POp.'&+*#G!~D1
```

Using the Malbolge interpreter provided at the decoded URL, the source code was executed. Upon execution, the program produced the final flag:

```
BITSCTF{d4mn_y0ur_r34lly_w3n7_7h47_d33p}
```

### tl;dr

* Extract `SaveMeFromThisHell.zip`.
* Analyze `Marlboro.jpg` with `binwalk` and discover embedded files.
* Recover `smoke.png` and `encrypted.bin` using `foremost`.
* Inspect `smoke.png` with `exiftool` → decode Base64 → obtain Malbolge tools URL.
* Run `zsteg` on `smoke.png` → extract 32-byte XOR key.
* XOR-decrypt `encrypted.bin` using the repeating key.
* Identify the output as Malbolge source code.
* Execute the Malbolge code using the online interpreter.
* Retrieve the flag: BITSCTF{d4mn_y0ur_r34lly_w3n7_7h47_d33p}

