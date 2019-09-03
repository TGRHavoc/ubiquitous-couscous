---
title: "Custom Images"
weight: 4
---

It's now fairly easy to use your own, custom images in the interface.

- Make a new folder in your `tileDirectory` directory (optional but, recommended)
- Put images into folder
- Add an entry to the `maps` array in the config.

Those are the only three steps you need!
Now, getting the images is a different matter.
If you have a custom "minimap" you use in game, you can probably use it with the interface as well. 
All you need to do is extract the images from the YTD files with a program like OpenIV.
If doing this, using the `minimap_sea` images will result in a much higher quality.

![Export](/images/7339a06b77d8594c0131883d1.png)

![Saving](/images/8ba2d745e29330e7b388de0ae.png)


## Extracting PNGs from YTD

If you have YTD files and, want to extract the PNGs for use in the map then this section should provide useful.

1. Download the YTDs you want to use.
   1. It is reccommended, for the best results, to use the `minimap_sea` YTDs as they're a much higher resolution than the normal `sea` files.
2. Install [PILLOW](https://pillow.readthedocs.io/en/stable/) for Python 3.x (Python 2.x is not supported)
   1. You can install this by running `pip3 install pillow` on most systems
3. Put all the YTDs into a folder
4. Copy the python scripts from [images/tiles/](https://github.com/TGRHavoc/live_map-interface/tree/master/images/tiles) into the folder.
   1. Make sure you copy **both** scripts
5. Run the `extract_png` script
   1. You can do this by running `python3 extract_png.py` on most systems
6. You should now have PNG files in the folder
7. Add the directory to the config to use.
