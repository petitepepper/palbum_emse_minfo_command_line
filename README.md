# palbum_emse_minfo_command_line

## **NAME**

 palbum - create a photo album from a set of photos taken by a digital camera or a smartphone. 



## **SYNOPSIS** 

palbum <INPUT-DIRECTORY> <OUTPUT-DIRECTORY> 

For example:

```shell
./palbum photos my_album
```





## **OVERVIEW**

The  **palbum**  program is a utility that helps you create simple static HTML photo albums from the  pictures taken with a digital camera or a smartphone stored in **INPUT-DIRECTORY**.  The resulting album is created in  **OUTPUT-DIRECTORY**.  

An already existing album  may be complemented with more photographs. 



## **DESCRIPTION**

 **INPUT-DIRECTORY** must exist and contain image files with embedded Exif data (at least the date the photo was taken). 

**OUTPUT-DIRECTORY**  may not exist as it will be created.  If it already exists and contains a  pre-generated photo album,  the latter will be complemented with the new photographs from **INPUT-DIRECTORY**. Be aware that older files with the same name will be overwritten with newest ones. 	

In the **OUTPUT-DIRECTORY**, the structure of your photo album will be as described below. 	

---

An  **index.html** file is present in **OUTPUT-DIRECTORY**, referencing each year in the album together with the number of photos taken each year. A click on the name of the year opens the album for this year. 	

A  directory  is created for every year a photograph  has been taken, with its name being the number of the year in the **YYYY** form. 	

Inside each year directories is an **index.html** file displaying the al- bum for this year, organised by month, oldest first, alongside direc- tories  representing  days  of the year  named  after the  **YYYY_MM_DD** format. 	

Each daily directory contains  the photos taken this very day  plus a **.thumbs**  directory in which are stored  thumbnails  for those photos. The photos are named according to their original name,  prefixed with the name of the directory they are in and a dash (-). Each thumbnail  has the  same name  as  the photograph  it represents postfixed with the **-thumb** string.  Thumbnails are smaller versions of their pictures with a height of 150 pixels.  However, they retain the aspect ratio of the original photo. 	

To go into the gory details, the  **index.html**  file found in the years directories  actually displays the thumbnails as a link to the actual picture, to prevent huge loading times.



<img src=".\src\html.png" />

---

The overall structure of the album  should resemble the following ex- ample where **OUTPUT-DIRECTORY** is **my_album**. 

```
y_album
├── 2011
│   ├── 2011_08_02
│   │   ├── 2011_08_02-img_6704.jpg
│   │   ├── 2011_08_02-img_6706.jpg
│   │   └── .thumbs
│   │       ├── 2011_08_02-img_6704-thumb.jpg
│   │       ├── 2011_08_02-img_6706-thumb.jpg
│   └── 2011_08_07
│       ├── 2011_08_07-img_6741.jpg
│       ├── 2011_08_07-img_6742.jpg
│       └── .thumbs
│           ├── 2011_08_07-img_6741-thumb.jpg
│           └── 2011_08_07-img_6742-thumb.jpg
├── 2014
│   └── 2014_07_20
│       ├── 2014_07_20-img_1095.jpg
│       ├── 2014_07_20-img_1096.jpg
│       ├── 2014_07_20-img_1097.jpg
│       └── .thumbs
│           ├── 2014_07_20-img_1095-thumb.jpg
│           ├── 2014_07_20-img_1096-thumb.jpg
│           ├── 2014_07_20-img_1097-thumb.jpg
├── 2017
│   ├── 2017_07_21
│   │   ├── 2017_07_21-213010.jpg
│   │   ├── 2017_07_21-213336.jpg
│   │   └── .thumbs
│   │       ├── 2017_07_21-213010-thumb.jpg
│   │       ├── 2017_07_21-213336-thumb.jpg
│   └── 2017_07_24
│       ├── 2017_07_24-140547.jpg
│       ├── 2017_07_24-140841.jpg
│       ├── 2017_07_24-141207.jpg
│       └── .thumbs
│           ├── 2017_07_24-140547-thumb.jpg
│           ├── 2017_07_24-140841-thumb.jpg
│           ├── 2017_07_24-141207-thumb.jpg
├── 2019
│   ├── 2019_07_17
│   │   ├── 2019_07_17-img_2156.jpg
│   │   ├── 2019_07_17-img_2180.jpg
│   │   └── .thumbs
│   │       ├── 2019_07_17-img_2156-thumb.jpg
│   │       ├── 2019_07_17-img_2180-thumb.jpg
│   ├── 2019_07_30
│   │   ├── 2019_07_30-img_2289.jpg
│   │   ├── 2019_07_30-img_2318.jpg
│   │   ├── 2019_07_30-img_2321.jpg
│   │   ├── 2019_07_30-img_2325.jpg
│   │   └── .thumbs
│   │       ├── 2019_07_30-img_2289-thumb.jpg
│   │       ├── 2019_07_30-img_2318-thumb.jpg
│   │       ├── 2019_07_30-img_2321-thumb.jpg
│   │       └── 2019_07_30-img_2325-thumb.jpg
│   └── 2019_07_31
│       ├── 2019_07_31-img_2331.jpg
│       ├── 2019_07_31-img_2335.jpg
│       └── .thumbs
│           ├── 2019_07_31-img_2331-thumb.jpg
│           ├── 2019_07_31-img_2335-thumb.jpg
└── index.html
```







## AUTHOR 

Written by the clever Wenjing YE :) 



## **REPORTING BUGS** 

**palbum** has no known bug  at that time.  However, if you find one, you may want to report it at <bugs@palbum.org>. 



## **COPYRIGHT** 

Copyright © 2020 Free Software Foundation, Inc. License  GPLv3+:  GNU GPL version 3 or later <https://gnu.org/licenses/gpl.html>. This is free  software:  you  are free to change and redistribute it. 

There is NO WARRANTY, to the extent permitted by law. 



## **SEE ALSO**

 ImageMagick(1), convert(1), mogrify(1) exif(1) bash(1)