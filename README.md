# Suturing for dVRK
## Setup guide
1. Follow [all of the installation instructions here,](https://github.com/divyabudihal/autonomous_surgical_camera) up to the "Autonomous Surgical Camera" heading
2. Navigate to the dvrk-ros respository and comment out line 67 of psm.py, to mute a bunch of extremely annoying warnings
3. cd to this directory and `pip install -r requirements.txt`, editing this file as necessary if any of the packages don't install. Unfortnately, newer versions of some packages are broken for Python 2.7, and it is necessary to mimic the configuration of the original system this was developed on, as much as possible. 
5. Launch the dvrk with the dvrk_full_cart_simulated.launch launchfile in this repository.
6. The most up-to-date simulation scene is `dVRK-suturing_center_wound.ttt`
7. Launch Jupyter notebook 

## Things that are broken/bad/spaghetti
- the dVRK doesn't track the desired poses strictly accurately, and sometimes the needle is rotated in the plane parallel to the dots, such that when we try to grab it on the opposite side, we miss slightly
- The circle fitting seems to be giving circles that are slighly above the plane that the dots lie on
- it seems that there's some sort of depth error in the camera