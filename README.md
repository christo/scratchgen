# ScratchGen

Project to research asset and code generation for [Scratch](https://scratch.mit.edu/) projects using available APIs.

Project stage: _pre-larval_

![Scratch Logo](img/Scratch-logo-sm.png)

There are several open source projects aimed at converting [Scratch](https://scratch.mit.edu/) projects to other forms 
(like JavaScript) and to read the scratch project file for analysis or re-rendering the blocks in the scratch forums.
Also, there are a handful that focus on the other direction: building up a scratch project from another 
representation, such as Tosh, a text version of the scratch block language. 

As of version 3, the Scratch project format is well published, understood and the source code for working with it is 
open source. The Scratch code itself may be the best API to generate code and other project assets.

## General Info

Scratch project files, `.sb3` files, are a zip file with assets and a json file.

The official [Scratch REST API](https://en.scratch-wiki.info/wiki/Scratch_API) provides access to project metadata, not 
the Scratch project files themselves. Community members have created many projects to fill that void.

The json elements closely represent the blocks with interconnections such as parent-child relationships and 
next-block relationships referenced via arbitrary, generated GUIDs. 

Scratch 3 is built in JavaScript using Blockly for the GUI. Earlier versions were built on Flash (Scratch 2.0) or 
Smalltalk (Scratch 1.4). Therefore, libraries that read or write earlier version scratch projects are not suitable 
for generating Scratch 3 projects directly. The Scratch 3 codebase has carefully handled backward compatibility such 
that projects written for previous versions of Scratch can be loaded but only if they are freshsly saved with 
Scratch 3 will the project files be available in the 3.0 format.

## Scratch Foundation and LLK

The Scratch Foundation [Life-Long Kindergarten](https://github.com/LLK) at MIT Media Lab seem to be two github 
entities for the same group and repositories appear at least partly mirrored under [LLK](https://github.com/LLK) and 
[scratchfoundation](https://github.com/scratchfoundation):

* [scratch-blocks](https://github.com/scratchfoundation/scratch-blocks) Scratch Blocks is a library for building 
 creative computing interfaces. 
* [scratch-vm](https://github.com/scratchfoundation/scratch-vm) Virtual Machine used to represent, run, and maintain the state of programs for Scratch 3.0
* [scratch-render](https://github.com/scratchfoundation/scratch-render) WebGL-based rendering engine for Scratch 3.0
* [scratch-gui](https://github.com/LLK/scratch-gui) Graphical User Interface for creating and running Scratch 3.0 projects.
* Several other component projects: Scratch Paint editor etc.

In some cases there are sometimes thousands of forks of these repositories.

## TurboWarp

Modified version of Scratch 3 with faster performance etc.

[TurboWarp](https://github.com/TurboWarp)

## Dr Scratch & Hairball

[cdchushig/drscratchv3](https://github.com/cdchushig/drscratchv3) seems to be the best fork deriving from the
static analysis tools _DrScratch_ and _Hairball_. Apparently starved for funding to pay the heroku bills and
stuck in eternal beta, [drscratch.org](http://drscratch.org/) does work to some extent as of April 2023 if you upload
the `.sb3` project file rather than expect it to be extract that for you from the scratch project page URL.

There are several other splinter repos for older versions:
[drscratchv3](https://github.com/AngelaVargas/drscratchv3),
[drscratchv2](https://github.com/AngelaVargas/drscratchv2),
[drscratch_2019](https://github.com/AngelaVargas/drScratch_2019) etc.

[Hairball](https://github.com/ucsb-cs-education/hairball/) seems to be the original work here and some hairball code
still lives on inside Dr Scratch. The [github fork network](https://github.com/jemole/hairball/network) is somewhat
unruly. [hairball-demo](https://github.com/ucsb-cs-education/hairball-demo) shows the original context and is written
up in an [academic paper](http://cs.ucsb.edu/~bboe/p/cv#sigcse13) by Bryce Boe in 2013.

The tldr for the paper is that existing static analysis tools relied upon for academic assessment and (somewhat
optimistically) "for students"  were not amenable to the visual programming environment, so like nearly every other
aspect of the software engineering toolchain and ecosystem, visual programming languages force them to be adapted or
rewritten.

## Tosh & Kurt

[tjvr/kurt](https://github.com/tjvr/kurt) is a Python 2 API for parsing Scratch 1.4 and 2.0 files, written by the same
developer (aka Blob8108) as [Tosh](https://github.com/tjvr/tosh) and [Tosh2](https://github.com/tjvr/tosh2) which are
text modes for Scratch implemented in JS.

[Tosh3](https://github.com/apple502j/tosh3) appears to be inspired by rather than derived from the above.

## Misc

* [getsb3](https://github.com/cdchushig/getsb3) API for downloading scratch projects in sb3 format. JavaScript, Docker.
* [scratchblocks](https://github.com/scratchblocks/scratchblocks) renders a faithful view of a scratch program's block
  shapes. Seems to be view only, not edit.
* [sb-edit](https://github.com/leopard-js/sb-edit) Some limited ability to download and modify scratch project files and assets.


