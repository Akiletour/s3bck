S3 Backup (s3bck)
=================

Put an archive, directory or file on S3 using s3bck and s3cmd

Installation
------------

1. Create an Amazon S3 account
2. Install and configure s3cmd
3. Download s3bck
4. Make the file executable
 
### 1. Create an Amazon S3 account [Amazon S3](http://aws.amazon.com/s3)

Go to Amazon S3 homepage, click on the "Sign up for web service" button in the right column and work through the registration. You will have to supply your Credit Card details in order to allow Amazon charge you for S3 usage. At the end you should posses your Access and Secret Keys.

### 2. Install and configure s3cmd

Install s3cmd on your server

``` bash
$ apt-get install s3cmd
```

And configure it

``` bash
$ s3cmd --configure
```


### 3. Download s3bck

``` bash
$ cd /usr/local/bin
$ wget https://raw.github.com/Akiletour/s3bck/master/s3cmd
```

### 4. Make the file executable

``` bash
$ sudo chmod +x /usr/local/bin/s3bck
```

Usage
-----

Example : I want to backup /var/www/inrage and put it on Amazon S3 in my bucket "inrage/backup"

``` bash
$ s3bck /var/www/inrage

- Compress the file (Y/n) ? y
- Archive name ([ARCHIVE-NAME]_201311091923.tar.gz): inrage
COMPRESSING FILE TO TAR
- Target S3 (BUCKET/DIRECTORY): inrage/backup
inrage_201311091923.tar.gz -> s3://inrage/backup/inrage_201311091923.tar.gz  [1 of 1]
128378 of 128378   100% in    1s    80.27 kB/s  done
REMOVING THE TEMPORARY FILE

SUCCESS: inrage_201311091923.tar.gz to s3://inrage/backup/inrage_201311091923.tar.gz
```

About
-----
s3bck is a [inRage](http://www.inrage.fr) initiative.
Created by Pascal GAULT.

Reporting an issue or a feature request
---------------------------------------

Issues and feature requests are tracked in the [Github issue tracker](https://github.com/Akiletour/s3bck/issues).


