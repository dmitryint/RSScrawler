#  RSScrawler
Main code by https://github.com/dmitryint commissioned by https://github.com/rix1337

## Version 1.1.3

Code used:

https://github.com/zapp-brannigan/own-pyload-plugins/blob/master/hooks/MovieblogFeed.py

https://github.com/Gutz-Pilz/pyLoad-stuff/blob/master/SJ.py

https://github.com/bharnett/Infringer/blob/master/LinkRetrieve.py

## Description:

This script scrapes MB/SJ for titles stored in .txt files and passes them on to JDownloader via the .crawljob format

## TLDR:

1. Enable folderwatch in JDownloader 2, then Download this script and install its prerequisites
2. Run and close the script once. It will automatically generate the ```Settings``` subdir with all the necessary files inside.
3. Set up the ```Settings.ini``` and your Lists completely, found in the ```Settings``` subdir.
4. Run the script!

## Launching the Script

Run RSScrawler.py

## Options

  ```--ontime```                  Run once and exit
  
  ```--log-level=<LOGLEVEL>```    Level which program should log messages (eg. CRITICAL, ERROR, WARNING, INFO, DEBUG, NOTSET )

## Settings:
*Your Settings.ini is located in the ```Settings``` subdir and will be recreated when removed*

Feel free to adjust the defaults to your liking, but ensure the paths inside the file are valid.

*The comments in rsconfig.py should help you in setting this up*

### patternfile/seasonslist/file:

A .txt list the script will use to crawl rss feeds.

Each line in Movies.txt should contain the title of a movie.
Each line in Shows.txt should contain the title of a show.

**These lists are set up with a placeholder line on the first run. To actually start crawling you need to fill the lists yourself**

### db_file:

The database file prevents duplicate crawljobs.

### crawljob_directoy:

Enable the Watch-Folder feature (experimental) in JDownloader first!

JDownloader crawljobs need to be placed in the ```folderwatch``` subdir of JDownloader, so adjust the Settings.ini accordingly.

### crawl3d:

Enable this option if (regardless of quality settings) you also want 3D versions of your Movies.txt to be added (in 1080p). 
By default HOU 3D-versions are blocked through the ignore option.

### enforcedl

Enable this option if you want to keep your collection DL (dual language).

If the script adds a Release that does not contain the DL tag it will start looking for another release that has two audio tracks, disregarding quality set.

For example: If 720p is your default resolution and a non-dl release is added, the script will also download a 1080p release if it has the DL tag (even though 1080p would otherwise be ignored).

### crawlseasons

Enable this option if you want to crawl MB for complete seasons.

```seasonslist``` should thus be pointed to your list of Shows and ```seasonsquality``` should be your desired quality for seasons. ```seasonssource``` can also be defined (default: bluray).

### Docker Container for RSScrawler:
https://github.com/rix1337/docker-rsscrawler
