# What is "Irokotoba"?

Irokotoba (from the Japanese Kanji for "Color" and "Words", so "Color of Words") is a small enthusiast program created to save texts, files and more to 2D images (saved as .iro-file).

# How did it came to be?

I sat down once, bored at work and wondered: We use QR-Codes to store links and they are able to store data, but what if data could be stored in images? I know, that this approach is not new, since it is possible to hide bytes in .pngs, but this is when I started looking for just that program.
And to fully disclose this: I had help from AI, but I tested everything by hand and tried a lot to ensure the program does what I expect from it. I am not a software engineer, but I also never claimed to be one in the first place.

# How to install and how does it work?

To install the program, download the Irokotoba.zip from this repository.
Extract the folder, which contains the main executeable and a folder "dictionaries" with the "latin_extended.cvd" inside.
Run the executeable and off you go! Adding more dictionaries is as simple as copying new .cvd-files to the folder.
**Disclaimer! You use the program at your own risk! Always use multiple forms of backup! Don't unpack files that are not your own!**

In both modes (Text- and File/Folder-Mode) the program encodes data into pixels (it encodes folders it creates a .zip-Archive) with specific RGB-values. For text-files, such as .txt, .js, .html, .log, etc..., it makes use of its .cvd-files (chroma visual dictionary) to encode most common words, phrases and commands into single pixels.
These pixels are then arranged to form an image (which can be viewed with an image viewer) and saved as an .iro file, which can be reverted into its original state.

# Why not use WINRAR or 7ZIP instead?

That's a good point. The output file will be very similar to an archive or even the original file, if used for already compressed file types. But for uncompressed images and data it can prove results that even go further than WINRAR or 7ZIP. The use case is very taylored, but very effective.

# How secure is it?

Irokotoba uses a Vigenère-style stream cipher on a token and byte level. The user-set password (which is optional) is hashed using SHA-256, which acts as a seed for a Pseudo-Random-Number-Generator. This PRNG stream then either offsets the raw RGB values (in File/Folder Mode) or it shifts the intext within the .cvd-array (in Text Mode).
If the user attempts to enter the wrong password, the software does still decrypt and decode the file, but the output will be nonsensical gibberish.
To make sure that one off color value doesn't corrupt the file, the .cvd-files have ranges assigned to characters, words or commands when used in Text-Mode. For File/Folder-Mode the .iro-file has those ranges itself.
Is it perfect? No, but who would guess that a file that looks like TV static contains important data?

# Why do I have to download the dictionaries seperately?

The program is created to ensure that storage-data can be saved. Including all Unicode characters and dictionaries of all languages in this program will make it useless, as the unused characters are eating up the storage you save. Why would you need German if you only encode text in plain English?

# Why does no dictionary for my language exist?

Like I said before: This is an enthusiast program, but I am working on a tool to make you able to create your own dictionaries (although it might take time, if you write them out yourself), which you can then upload and share with others.
For now I can only offer German, Englisch and the basic dictionary (Latin characters).

# How efficient is Irokotoba and what are its boundaries?

The best case is to encode text files and scripts like .txt, .html, .json, .log and alike. In my tests the data saved was at about 40-70% (depending on the type and the dictionaries used). It can also work well for uncompressed forms of data like .wav, .raw, .obj or .db. Here I was able to get results that are between 20 and 45%.
The worst case are pre compressed types of files and other programs like .exe, .pdf, .mp4 or .jpeg. In those cases don't expect any advantage over 10% if at all (some files got larger in testing).

The limit of the program is dependend on your systems's memory. To make sure that the program doesn't crash, I have the following rule of thumb:
"Usable Memory * 90% / 3" (eg. 48GB * 90% / 3 = 14.4GB file size to give to the program)
Be aware that encoding files can take a massive amount of time with larger file size. (An 1GB folder took me about 2-3 minutes.)

# What will come?

I am still working on some changes, but I don't expect the file format to change from here on now, meaning that if you create an .iro-file now, you should still be able to decode it in 15 years from now.
When I consider my work done on this program, I will make it completely open-source, since I want then the community to take it away, add and improve to create something that might become very useful in the future.
If you have some suggestions, questions or constructive feedback, please let me know.

You read the entire README (or just scrolled to the bottom like in all the EULA-forms?), would you like to give it a try?
