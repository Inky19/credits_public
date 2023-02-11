# Frums - Credits EX animation
A fork of plaaosert's *Frums - Credits animation* repository to fix some issues on Linux.

In particular, the `keyboard` library has been replaced by `pynput` to avoid having to run the animation as root. The terminal is also now cleared at startup.


Tested on Python 3.10.9 (Manjaro 22.0.2) 

# Media credits
- All animation work done by plaaosert:
  - https://github.com/plaaosert/credits_public
- Song credit: Frums - Credits EX https://soundcloud.com/frums/credits-ex
- Song is not included in this repository. Read /media/README.txt.

 
# Video

You can watch the animation on plaaosert's YouTube channel:
- https://youtu.be/o3cKQzrtFgQ
 
 
# How to run
 Run `credits.py`. Required libraries:
 - just-playback https://github.com/cheofusi/just_playback (See [known issue](#known-issue))
 - pynput https://github.com/moses-palmer/pynput
 - colorama https://github.com/tartley/colorama -
 the version of colorama used is also included inside this repository.

# Controls

The original key bindings have been changed:
- Selecting an option in the main menu is now based on letters (instead of numbers)
- During animation playback:
  - `P` pauses the playback
  - `K`, `L` and `M` increase the speed of the animation (by a factor of 3, 7 and 15 respectively)

This change was made to support more keyboard layouts (numbers and some symbols require a combinaison of keys on other layouts such as azerty, which is not supported)

# Known issue

## Error `illegal hardware instruction` 
This problem is due to the `just-playback` library on Linux, as the binaries are apparently not compiled correctly.    
A simple fix is to reinstall the library by first running
``` 
pip uninstall just_playback 
```
and then building the library with 
``` 
pip install --no-binary just_playback just_playback 
```
Solution by cheofusi:  
https://github.com/cheofusi/just_playback/issues/21#issuecomment-1246424734