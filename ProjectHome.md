# iPhotoFS #

iPhotoFS is a read-only filesystem for iPhoto collections on the Mac

It's useful for exploring your iPhoto library on other PCs or consumer electronic devices.  It's also useful for backing up your iPhoto library (even to non-macs while retaining its structure.)

You can easily interfact with your iPhoto collection using the Finder and command line utilities like `find` and `rsync`.

## Example Usage ##
```
# list my flagged photos
$ ls /Volumes/iphotofs/Albums/Flagged/
DSCF0472.JPG	IMG_0017.JPG	IMG_2031.JPG	MIT Group.JPG	P1210042.JPG

# Export all of my albums to my PC
$ cp -R /Volumes/iphotofs/Albums /Volumes/MyPC/

# Show all photos taken in 2009-01
$ ls  /Volumes/iphotofs/Dates/2009-01

```

## Installation ##
You must first install MacFUSE (http://code.google.com/p/macfuse/downloads/list)   You also need to be running iPhoto 6 or greater.

Then simply run the iPhotoFS app and it will open up a new Finder window with the new filesystem selected.

## Details ##

The file system is a [MacFuse](http://code.google.com/p/macfuse/) user mode filesystem that reads iPhoto's AlbumData.XML file.

Here's the current folder organization:

  * `/Volumes/iphotofs/Albums` contains subdirectories for all iPhoto albums.
  * `/Volumes/iphotofs/Rolls` contains all rolls.
  * `/Volumes/iphotofs/Dates` contains subdirectories for all Years/Months.


The original filenames are preserved when possible.  In the event of name collision between two different files, the names are uniquified by prepending the roll ID.

## Screenshots ##

_Browsing iPhoto rolls in the Finder_

![http://thebogles.com/images/iPhotoFS.png](http://thebogles.com/images/iPhotoFS.png)

_Browsing iPhoto by date on a PC_

![http://thebogles.com/images/iphotofs3.png](http://thebogles.com/images/iphotofs3.png)


_Browsing iPhoto events on a networked Blu-Ray player_

![http://thebogles.com/images/iphotofs1.jpg](http://thebogles.com/images/iphotofs1.jpg)