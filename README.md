Final project for the course Computational Music Creativity.

## Introduction
In this project, I made a pd patch to imitate some sounds in nature, and a control board to manipulate and present these sounds with Mobmuplat.In general, the whole project can be divided into 2 main parts, a pd patch and an OSC file.

### Pd patch
The Pd patch contains 3 parts, sound-generating, sound-playing, and GUI-linking:

![Pd Patch](https://github.com/qiaoyx3170/Summer-Night/blob/main/Screenshot%20%20of%20Pd%20patch.png?raw=true)

The sounds in sound-generating parts (grey) are independent of each other. Thus, every single sound can be extracted to be a single pd patch. To make it clear and easy to understand, I use the send and receive objects instead of linking them to dac~ directly. 

In the sound-playing part (green), I use the receive object to receive the audio signal from the sound-generating part and send the signal to dac~

In the GUI-linking part (orange), I use the route object to read the address from Mobmuplat. Among these addresses, the insects and bird_voice are read in packs, in order to connect to the objects in Mobmuplat. The other addresses are read directly and send the trigger signal to the corresponding sound-generating patches. The insects and bird_voice addresses are unpacked first and sent to different inlets in related sound patches.
