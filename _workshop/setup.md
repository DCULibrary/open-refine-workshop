---
title: Setup and Install     # The title of the page
date: 0000-01-02    # Page order is set by date
---

For this workshop you should have OpenRefine installed and a sample dataset downloaded:

### Downloading OpenRefine

* Download OpenRefine from <https://openrefine.org/download.html>
There are versions for Windows, Mac OS X and Linux. The current stable version which this workshop has been tested with is __version 3.3__

* Full download instructions: <https://docs.openrefine.org/manual/installing/>

* Current versions of the “Windows kit with embedded Java” and “Mac kit” include everything you need to run OpenRefine. The “Linux kit” and traditional “Windows kit” require a “Java Runtime Environment” (JRE) installed on your system (see notes below).

### Downloading the sample dataset

* Download the sample dataset from <http://tiny.cc/dcuopenrefine> which is taken from the __[*Carpentries*](https://carpentries.org)__ OpenRefine lessons, which this lesson is based on (see credits).

### Installing OpenRefine

* When you download OpenRefine for __Windows__ or __Linux__ from the address above, you are downloading a zip file.

* To install OpenRefine you simply unzip the downloaded file wherever you want to install the program. This can be to a personal directory or to an applications or software directory - OpenRefine should run wherever you put the unzipped folder. The location should be a “local” drive as problems have been reported trying to run OpenRefine from a Network drive.

* __The options “Windows kit with embedded Java” and “Mac kit” include Java as part of the package. You do not need to install Java if you use one of these kits. This is the preferred method on Windows and Mac systems.__

* On Windows, if you use the traditional “Windows kit” without embedded Java, you will need a “Java Runtime Environment” (JRE) on your system. If you do not already have JRE or JDK installed, you can visit Adopt OpenJDK or Oracle Java to download an installer package. Please note that Oracle significantly changed their license terms in 2019 limiting it to “personal use” with out a paid license. If you use OpenRefine at work or in research, OpenJDK is preferred.

* If you are downloading OpenRefine for Mac, you a re downloading a ‘dmg’ (disk image) file which you can open, and then drag the OpenRefine application to an appropriate folder on you computer.

* On Linux a “Java Runtime Environment” (JRE) will be required to run OpenRefine. If you do not already have JRE or JDK installed on your system, most distribution repositories will contain OpenJRE / OpenJDK packages. Install the default version available from your distribution. For example, on Ubuntu/Debian: sudo apt install default-jre.

* OpenRefine does not support Internet Explorer. Please use Firefox, Chrome or Safari instead

### Running OpenRefine:
* Windows: Navigate to the folder where you’ve installed OpenRefine and either double-click ‘google-refine.exe’ (for Google Refine 2.5), ’openrefine.exe’ (for OpenRefine 2.6) or ‘refine.bat’ (for either)
* Linux: Navigate to the folder where you’ve installed OpenRefine in a terminal window and type ‘./refine’
* Mac: Navigate to where you installed OpenRefine and click the OpenRefine icon

The interface to OpenRefine is accessed via a web browser. When you run Refine normally this should open a window in your default web browser pointing at the address http://127.0.0.1:3333. If this doesn’t happen automatically you can open a web browser and type in this address.

### Getting Help
You can find support, documentation and tutorials on using OpenRefine in various places online including:

* The OpenRefine Wiki https://github.com/OpenRefine/OpenRefine/wiki
* The ‘Free your metadata’ site http://freeyourmetadata.org/
* The OpenRefine mailing list and forum http://groups.google.com/d/forum/openrefine
