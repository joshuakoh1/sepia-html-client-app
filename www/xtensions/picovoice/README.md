# Porcupine Wake-Word Engine by Picovoice

This is the client extension for Porcupine wake-word detection by [Picovoice](https://github.com/Picovoice/porcupine).
All wake-words found here are taken from their official GitHub account and are under Apache 2.0 license except "Hey SEPIA" that was generously created for this project.

## Switching the Wake-Word

Open `wakeWords.js` and change the entries for `SepiaFW.wakeTriggers.porcupineWakeWords` and `SepiaFW.wakeTriggers.porcupineVersion` (if required).  
To switch the wake-word to "raspberry" for example enter the following:
```
SepiaFW.wakeTriggers.porcupineVersion = "1.5";
SepiaFW.wakeTriggers.porcupineWakeWords = ["Raspberry"];
```

This will automaticall load the file: `keywords/1.5/raspberry_wasm.ppn`.  
  
The library for Porcupine engine v1.4 is included by default since this is the version "Hey SEPIA" was created for. v1.5 and v1.6 are available via SEPIA's GitHub repository.
You can use the `download_wasm.sh` or `download_wasm.bat` file to download them directly to your folder, by default they will be loaded to browser cache at first start of the Porcupine engine.  
After you've downloaded the files set `SepiaFW.wakeTriggers.porcupineVersionsDownloaded = true;` in your `wakeWords.js`.

## Using multiple Wake-Words at the same time

It is possible to load more than one wake-word by using the alternate format of `SepiaFW.wakeTriggers.porcupineWakeWords`.
To do this you need to copy the data from the wake-word files to your `wakeWords.js` like this:
```
SepiaFW.wakeTriggers.porcupineVersion = "1.4";
SepiaFW.wakeTriggers.porcupineWakeWords = {
	'hey sepia': new Uint8Array([
		0xE0, 0x33, 0x02, 0xB3, 0x7D, 0x67, 0xEC, 0xA6, 0x39, 0x01, 0x70, 0x44, 
		0x70, 0xB2, 0xCE, 0x48, 0x05, 0xE5, 0x45, 0x72, 0xC4, 0x8E, 0x03, 0xBF, 
		0x32, 0x90, 0x33, 0xA9, 0x9E, 0x8A, 0x53, 0x17, 0x00, 0x69, 0x26, 0x2F, 
		0x7E, 0xF4, 0xDD, 0x9B, 0x8A, 0xF4, 0xAC, 0x9B, 0x51, 0x99, 0xEC, 0x33, 
		0x68, 0xFF, 0xEB, 0x72, 0x7D, 0x10, 0x0B, 0xAD, 0xD2, 0x1F, 0xD9, 0x0C, 
		0x54, 0x0E, 0xF9, 0xBF, 0x6B, 0xB3, 0x21, 0xD4, 0x59, 0xBD, 0xFF, 0x4E, 
		0x18, 0x4B, 0xCE, 0x31, 0xBC, 0x4F, 0xBC, 0xF4, 0xDA, 0xA6, 0x0D, 0x6C, 
		0x5D, 0xA5, 0x50, 0x0F
	]),
	'yellow': new Uint8Array([
		0x6f, 0x7d, 0x2c, 0x10, 0xcb, 0xf0, 0x76, 0x1b, 0xee, 0xeb, 0x80, 0xaa,
		0xe1, 0xa5, 0xfa, 0x53, 0xe3, 0xce, 0x4b, 0x59, 0x7d, 0xeb, 0xe3, 0x11,
		0x13, 0x87, 0x61, 0xa5, 0xef, 0x04, 0x04, 0x37, 0x63, 0xf6, 0x63, 0x91,
		0x44, 0x22, 0xf2, 0x50, 0xab, 0xb7, 0x35, 0x8c, 0xcf, 0x33, 0xf7, 0xc1,
		0xf1, 0x06, 0x6c, 0x37, 0x6b, 0x2d, 0x50, 0x0e, 0x1c, 0x1c, 0xee, 0x9d,
		0x3d, 0x56, 0xa6, 0x54, 0x51, 0xb2, 0xf4, 0x3d, 0x76, 0x7b, 0xcf, 0x4c
	])
};
```

This example will activate "Hey SEPIA" AND "yellow" at the same time.  
NOTE: You CANNOT mix wake-words for different versions!

### Currently available wake-words

These are the wake-words available in SEPIA Client v0.22.0.

#### v1.4

hey sepia
navy blue
ok lamp
orange
purple
white
yellow

#### v1.5

alexa
americano
avocado
blueberry
bumblebee
caterpillar
christina
dragonfly
flamingo
francesca
grapefruit
grasshopper
iguana
picovoice
pineapple
porcupine
raspberry
terminator
vancouver

#### v1.6

americano
blueberry
bumblebee
crimson
deep pink
deep sky blue
dim gray
fire brick
forest green
grapefruit
grasshopper
hey edison
hey pico
hot pink
lavender blush
lime green
magenta
midnight blue
papaya whip
peach puff
picovoice
porcupine
sandy brown
terminator
white smoke