# Installing apps on ColonialOne

In this example I am going to install [FLASh](https://ccb.jhu.edu/software/FLASH/) Fast Length Adjustment of Short reads.

First I need to identify how to obtain the installation files. This might be a GitHub repository or perhaps a tar file containing source code. For FLASh the 


Set your permissions so everyone in CBI can access the software. I use umask, which changes the default permissions for new files:

```bash
umask 0002
```

### 1. Create a place for the app to live

Go to /groups/cbi/shared/apps and create a new directory for the app:

```bash
cd /groups/cbi/shared/apps
mkdir flash
cd flash
```

#### Subdirectories

It is sometimes important to archive previous versions of softwIn generally, I like to organize subdirectories for each version of the software. In addition, I create a directory called `archive` for storing the original source codes.

```bash
mkdir archive
```

### 2. Obtain the installation files

Next obtain the installation files. You can download the file on your local machine then upload to the archive directory using cyberduck. Or, better yet, use `wget` to download directly on ColonialOne, and document the URL you used to download.

```bash
cd archive
wget http://downloads.sourceforge.net/project/flashpage/FLASH-1.2.11.tar.gz
cd ..
```

### 3. Build the software

Now, follow the directions for building the software. FLASh is a typical 

```bash
# Extract the archive
$ tar xzf archive/FLASH-1.2.11.tar.gz

# Created a new directory, FLASH-1.2.11
# Shorten the name to just the version (because I like to)
$ mv FLASH-1.2.11 1.2.11

# Change to version directory
cd 1.2.11/

# Run make
make
```

Once you have finished building the app, you will need to create a modulefile so it can be loaded.

### 4. Tell C1 how to load the app

A detailed description of a modulefile is 

The most important part of your module file is the prependPath command. When calling `module load flash`, lmod will parse the module file and add this to the beginning of your path. Similarly, when unloading a module, this path will be removed from `$PATH`.

Here is the example module file I created for flash.

```bash
$ cd /groups/cbi/shared/modulefiles
$ mkdir flash
$ cd flash
```

Within this directory, create a file with the version.



Thats it! The modul

```
module load flash




