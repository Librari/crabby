
<img src="https://raw.github.com/mainroach/crabby/master/icon.jpg" width="256" align="right" hspace="20">

# CRABBY #
A texture compression format for spritesheets

## Why does the encoder only take TGA files? ##
Simply to simplify distribution. The code gets more complex when you start adding libraries for JPG and PNG processing.


## Building the encoder ##
Currently, a visual studio project is provided. For ideal output, you should build the crabby.exe file to the ../../bin folder, so it can interact with the source textures

## Running the encoder ##
Crabby will take, as an input a text file which lists what images to consume and process, and output a set of files which start with 'outtextureprefix'
* crabby.exe <texturelilst> <outtextureprefix>
* e.g. crabby.exe in-textures/crab/imglist.txt out-textures/crab
* e.g. crabby.exe in-textures/jelly/imglist.txt out-textures/jellyfish

## What to do with the output? ##
3 files are output from the encoding:
* name_blockatlas.tga
	* This file is a 4 channel 32bpp texture
	* THIS is the texture you can further encode with dxt/etc/jpg/png
* name_frames.raw
	* This image contains the bin-packed control textures. Each texture is quarter resolution from the origional, and contains indexes into the pallete texture
* name_metadata.raw
	*  This binary file contains the frame data for the input images; this is similar to what you would get out of texture packer

