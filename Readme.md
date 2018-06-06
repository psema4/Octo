Octo for UniCHIP8
=================

This Octo fork adds compiler support for UniCHIP8 extended opcodes.

* [CHIP-8](http://mattmik.com/chip8.html) is a virtual machine designed in 1977 for programming video games
* [Octo](http://johnearnest.github.io/Octo/) is a high level assembler, disassembler and simulator for the CHIP-8
* [UniCHIP8](https://github.com/psema4/unichip8) is a CHIP-8 implementation for Unity 3D

<img src="https://raw.githubusercontent.com/psema4/unichip8/master/Assets/UniCHIP8/unichip8-v1.png" width="640" />

UniCHIP8 Extensions
-------------------

To refer to UniCHIP8 extended opcodes in .u8o source files, set the necessary register values followed by a UniCHIP8 
instruction token:

    Misc
      uc-test              uc-call              uc-broadcast
      uc-send              uc-reparent          uc-destroy

    Transform
      uc-move              uc-rotate            uc-scale
      uc-moveX             uc-rotateX           uc-scaleX
      uc-moveY             uc-rotateY           uc-scaleY
      uc-moveZ             uc-rotateZ           uc-scaleZ
	  uc-lookAt

    Create
      uc-create            uc-createCube        uc-createSphere
      uc-createCylinder    uc-createCapsule     uc-createPlane
      uc-createQuad        uc-createEmpty		uc-createDirectionalLight
	  uc-createPointLight  uc-createAreaLight   uc-createSpotLight

    Materials
      uc-addMaterial       uc-setMaterialColor
	  
	Lights
	  uc-setLightColor     uc-setLightIntensity

    Machine state
      uc-clockMultiplier   uc-logging           uc-compatiblityMode
      uc-pause             uc-halt              uc-powerDown


Example

    # Center the camera in UniCHIP8's limited
    # world-space, pulled back 2 units on the
    # z axis.
    
    i  := unity-main-camera
    v0 := 127
    v1 := 127
    v2 := 125
    uc-move

See the [UniCHIP8 folder](https://github.com/psema4/Octo/tree/feature/UniCHIP8/UniCHIP8) for more examples. For 
details on the UniCHIP8 extension opcodes, see the 
[UniCHIP8](https://github.com/psema4/unichip8) project.

Compiling & Testing UniCHIP8 Rom files
--------------------------------------

To compile a .u8o source file from the command-line, ensure you have the compiler:

* ensure you have Node.js installed
* clone this repo to your filesystem

Then to compile programs:

* cd into the Octo folder
* compile a source file: node ./octo UniCHIP8/demo.u8o UniCHIP8/out/demo.uc8
* copy the output file demo.uc8 into the Roms folder of your UniCHIP8 project
* set the ROM file property on a UniCHIP8 component to "demo.uc8"
* play your scene in the Unity Editor to test

Licensing
---------
Octo, along with all its associated documentation, examples and tooling, are made available under the MIT license. See LICENSE.txt for additional details. If for any reason this is insufficiently flexible or permissive for some application, please contact John Earnest with your request. Contributions to this repository are welcome, with the understanding that they will fall under the same licensing conditions.

UniCHIP8 is also MIT licensed.
