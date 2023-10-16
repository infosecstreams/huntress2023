[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/449ac714104c4f3bb151d74dce3388cd)](https://www.codacy.com/manual/rafiibrahim8_2/iSteg?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=rafiibrahim8/iSteg&amp;utm_campaign=Badge_Grade)
[![HitCount](http://hits.dwyl.com/rafiibrahim8/iSteg.svg)](http://hits.dwyl.com/rafiibrahim8/iSteg)
# iSteg
#### A little steganography. Hiding text or file inside an image using LSB method
iSteg can hide your file inside an image.

[https://github.com/rafiibrahim8/iSteg](https://github.com/rafiibrahim8/iSteg)



## Why iSteg?
- You can choose how many least significant bit to use during creation of the file. Thus even less reduction in image quality.
- Supports encryption. File/Message can be encrypted inside the image using AES CBC method. With 256 bit key.
- Come with two flavor Command Line and GUI application. Select your preferred flavor.

## Requirements
- Just a computer with Java installed in it.

## Running the program
### GUI 
  - Just double click on the `.jar` file. If you are on Linux do `chmod +x iSteg-v2.1_GUI.jar` before executing the jar.
### Command Line
  - Simply open a Terminal/Command Prompt and type `java -jar iSteg-v2.01_CLI.jar`.
  
## Downloads
- GUI: [GUI Release v2.1](https://github.com/rafiibrahim8/iSteg/releases/tag/v2.1)
- Command Line: [Release v2.01](https://github.com/rafiibrahim8/iSteg/releases/download/v2.01/iSteg-v2.01_CLI.zip)
  #### Verify Download
    `SHA256(iSteg-v2.1_GUI.jar) : 668655387e0cdfc08317f3ee5be74e3a3e040f23bf5619e64abd1eaf7afeb0b3`
    `SHA256(iSteg-v2.01_CLI.zip) : 4c83d24e7f0b1e07a8f6c63615c2d68e532c5dc8edfaabf8fe4856e2b5afc712`
    
## Screenshots
- GUI
![Graphical User Interface (GUI)](https://i.imgur.com/7ZCfVQZ.png)

- CLI
![Command Line Interface (CLI)](https://i.imgur.com/4dHuyrz.png)

## FAQ
- What is top image & bottom file?

  Ans: Top image is the image in which the your file will be hidden. Here bottom file is your file to be hidden. 
