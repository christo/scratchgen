# ScratchGen

Project to research asset and code generation for [Scratch](https://scratch.mit.edu/) projects using
available APIs.

Project stage: _pre-larval_

The TurboWarp fork of the official Scratch looks like a good way to build scratch projects from
JavaScript programmatically

![Scratch Logo](img/Scratch-logo-sm.png)

There are several open source projects aimed at converting [Scratch](https://scratch.mit.edu/)
projects to other forms (like JavaScript) and to read the scratch project file for analysis or
re-rendering the blocks in the scratch forums. Also, there are a handful that focus on the other
direction: building up a scratch project from another representation, such as Tosh, a text version
of the scratch block language.

As of version 3, the Scratch project format is well published, understood and the source code for
working with it is open source. The Scratch code itself may be the best API to generate code and
other project assets.

## General Info

Scratch project files, `.sb3` files, are a zip file with assets and a json file.

The official [Scratch REST API](https://en.scratch-wiki.info/wiki/Scratch_API) provides access to
project metadata, not the Scratch project files themselves. Community members have created many
projects to fill that void.

The json elements closely represent the blocks with interconnections such as parent-child
relationships and
next-block relationships referenced via arbitrary, generated GUIDs.

Scratch 3 is built in JavaScript using Blockly for the GUI. Earlier versions were built on Flash
(Scratch 2.0) or Smalltalk (Scratch 1.4). Therefore, libraries that read or write earlier version
scratch projects are not suitable for generating Scratch 3 projects directly. The Scratch 3 codebase
has carefully handled backward compatibility such that projects written for previous versions of
Scratch can be loaded but only if they are freshsly saved with Scratch 3 will the project files be
available in the 3.0 format.

## TurboWarp

Better version of Scratch 3 with faster performance etc. Not official but it seems like the best
thing to build on. Developer docs are extensive. Has TypeScript types.

[TurboWarp](https://github.com/TurboWarp)

## Scratch MIT Official

The Scratch Foundation and Life-Long Kindergarten (LLK) at MIT Media Lab seem to each have a github
entity for the same group and their repositories appear to be highly
interlinked: [LLK](https://github.com/LLK)
and [scratchfoundation](https://github.com/scratchfoundation).

The JavaScript codebases use the CommonJS module system: `const foo = require('foo');`

### scratchfoundation

* [scratch-blocks](https://github.com/scratchfoundation/scratch-blocks) Scratch Blocks is a library
  for building
  creative computing interfaces.
* [scratch-vm](https://github.com/scratchfoundation/scratch-vm) Virtual Machine used to represent,
  run, and maintain the state of programs for Scratch 3.0
* [scratch-render](https://github.com/scratchfoundation/scratch-render) WebGL-based rendering engine
  for Scratch 3.0
* [scratch-paint](https://github.com/scratchfoundation/scratch-paint)
* [scratch-svg-renderer](https://github.com/scratchfoundation/scratch-svg-renderer)
* [scratch-semantic-release-config](https://github.com/scratchfoundation/scratch-semantic-release-config)
* [scratch-renovate-config](https://github.com/scratchfoundation/scratch-renovate-config)
* [scratch-storage](https://github.com/scratchfoundation/scratch-storage)
* [scratch-audio](https://github.com/scratchfoundation/scratch-audio)
* [scratch-parser](https://github.com/scratchfoundation/scratch-parser) Validation and parsing for
  Scratch `.sb2`
  projects
* [scratch-render-fonts](https://github.com/scratchfoundation/scratch-render-fonts)
* [scratch-asset-types](https://github.com/scratchfoundation/scratch-asset-types)
* [scratch-sb1-converter](https://github.com/scratchfoundation/scratch-sb1-converter) Convert
  Scratch .sb files (for
  Scratch 1) to Scratch 2 (.sb2) in JS.
* ... more rando stuff

### LLK

* [scratch-www](https://github.com/LLK/scratch-www) Standalone web client for Scratch
* [scratch-gui](https://github.com/LLK/scratch-gui) Graphical User Interface for creating and
  running Scratch 3.0 projects.
* [scratch-l10n](https://github.com/LLK/scratch-l10n) localisation, international translations
* [scratch-resources](https://github.com/LLK/scratch-resources) Source files and images for
  translators to translate Scratch materials
* [eslint-config-scratch](https://github.com/LLK/eslint-config-scratch) Shareable ESLint config for
  Scratch
* [scratch-desktop](https://github.com/LLK/scratch-desktop) Scratch 3.0 as a self-contained desktop
  application
* [scratch2-project-analyzer](https://github.com/LLK/scratch2-project-analyzer) Tools for analyzing
  Scratch 2.0 projects
* [scratchjr-website](https://github.com/LLK/scratchjr-website) Code for the Scratch Jr Website
* [scratch-analysis](https://github.com/LLK/scratch-analysis) Analysis tool for summarizing the
  structure, composition, and complexity of Scratch programs.
* [scratch-link](https://github.com/LLK/scratch-link) Device interoperability layer for Windows and
  MacOS
* [paper.js](https://github.com/LLK/paper.js) LLK fork of js vector graphics scripting library
* ...several other component and utility projects.

In some cases there are sometimes thousands of forks of these repositories.

## Phosphorus and Bismuth

Phosphorus was a Scratch to JavaScript compiler. Forkphorus is the new Phosphorus apparently but the
developer acknowledges TurboWarp is better:

* [forkphorus](https://github.com/forkphorus/forkphorus)
* [phosphorus](https://github.com/trumank/phosphorus)
* [bismuth](https://github.com/adroitwhiz/bismuth)
* Example project used to create an app store mobile game by converting phosphorus-generated js to
  iOS and Android using Adobe PhoneGap. [Roy the RPG](https://github.com/nitrodragon/royroyroyroy)

See also this HTML5 block editor implementation using phosphorus and blockly:
[Argon](https://github.com/jgordon510/Argon)

## Dr Scratch & Hairball

[cdchushig/drscratchv3](https://github.com/cdchushig/drscratchv3) seems to be the best fork deriving
from the static analysis tools _DrScratch_ and _Hairball_. Apparently starved for funding to pay the
heroku bills and stuck in eternal beta, [drscratch.org](http://drscratch.org/) does work to some
extent as of April 2023 if you upload the `.sb3` project file rather than expect it to be extract
that for you from the scratch project page URL.

There are several other splinter repos for older versions:
[drscratchv3](https://github.com/AngelaVargas/drscratchv3),
[drscratchv2](https://github.com/AngelaVargas/drscratchv2),
[drscratch_2019](https://github.com/AngelaVargas/drScratch_2019) etc.

[Hairball](https://github.com/ucsb-cs-education/hairball/) seems to be the original work here and
some hairball code
still lives on inside Dr Scratch.
The [github fork network](https://github.com/jemole/hairball/network) is somewhat
unruly. [hairball-demo](https://github.com/ucsb-cs-education/hairball-demo) shows the original
context and is written
up in an [academic paper](http://cs.ucsb.edu/~bboe/p/cv#sigcse13) by Bryce Boe in 2013.

The tldr for the paper is that existing static analysis tools relied upon for academic assessment
and (somewhat optimistically) "for students"  were not amenable to the visual programming
environment, so like nearly every other aspect of the software engineering toolchain and ecosystem,
visual programming languages force them to be adapted or rewritten.

## Tosh & Kurt

* [tjvr/kurt](https://github.com/tjvr/kurt) is a Python 2 API for parsing projects saved in Scratch
  1.4 and 2.0.
* [Tosh](https://github.com/tjvr/tosh) and [Tosh2](https://github.com/tjvr/tosh2) are text to
  scratch generators implemented in JS, the same author as kurt.
* [Tosh3](https://github.com/apple502j/tosh3) appears to be inspired by rather than derived from the
  above, written in JS by [apple502j](https://github.com/apple502j).

## Misc

* [getsb3](https://github.com/cdchushig/getsb3) API for downloading scratch projects in sb3 format.
  JavaScript, Docker.
* [scratchblocks](https://github.com/scratchblocks/scratchblocks) renders a faithful view of a
  scratch program's block shapes. Seems to be view only, not edit.
* [sb-edit](https://github.com/leopard-js/sb-edit) Some limited ability to download and modify
  scratch project files and assets.
* [Xeltalliv/ScratchTools](https://github.com/Xeltalliv/ScratchTools) misc standalone utilities for
  Scratch 3
  written in JavaScript.
* [MegaApuTurkUltra/ScratchTools](https://github.com/MegaApuTurkUltra/ScratchTools) follower stats
  and audio visualisation for Scratch 2 written in Java.
* https://github.com/RexScratch/PenTextEngineInjector
* https://github.com/RexScratch/PenFontEngineInjector
* https://github.com/RexScratch/PFEDataGenerator