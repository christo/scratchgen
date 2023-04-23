# ScratchGen

Project to play with generating scratch project code using available APIs.

## General Info

Scratch project files, `.sb3` files, are a zip file with assets and a json file.

The official Scratch API only provides project metadata, and does not provide a way to obtain the scratch project files themselvess, nor to modify those project files programmatically. However, community members have created many projects to fill that void.

Scratch 3 is built with Blockly

## APIs and Projects to Check Out

All are github user/repo format projects unless otherwise noted. In the case of forks, some are listed because there may be divergent features and worthy benefits.

* Scratch Foundation repositories appear mirrored under [LLK](https://github.com/LLK) and [scratchfoundation](https://github.com/scratchfoundation):
    * [scratch-blocks](https://github.com/scratchfoundation/scratch-blocks) 
* [getsb3](https://github.com/cdchushig/getsb3) API for downloading scratch projects in sb3 format. JavaScript, Docker.
* [scratchblocks](https://github.com/scratchblocks/scratchblocks) renders a faithful view of a scratch program's block shapes. Seems to be view only, not edit.
* [sb-edit](https://github.com/leopard-js/sb-edit) Some limited ability to download and modify scratch project files and assets.
* [drscratchv3](https://github.com/AngelaVargas/drscratchv3) static analysis of scratch project files. The old versions are [drscratchv2](https://github.com/AngelaVargas/drscratchv2) [drscratch_2019(https://github.com/AngelaVargas/drScratch_2019). Noteable fork: [cdchushig/drscratchv3](https://github.com/cdchushig/drscratchv3)

The following are outdated:

* [tjvr/kurt](https://github.com/tjvr/kurt) Python 2 API for parsing Scratch 1.4 and 2.0 files. 
