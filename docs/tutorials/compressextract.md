---
title: "Compressing and Extracting Files on the RCP"
author: "Melissa Velez"

tags:
  - zip
  - unzip
  - gunzip
  - compress
  - uncompress
  - extract
---

Compressing and Extracting Files {#compressextract} 
================

At this time, only one file can be downloaded from the RCP at a time. Should you need to download more than one file, one option is to compress them (e.g., zip) into one folder for download. Additionally, you may need to extract compressed files you uploaded onto the RCP. This tutorial provides information on how to use system-wide tools to compress and extract files.  

These commands can be issued in the terminal of your research software of choice.

## zip 

The zip command can be used to zip one or more files into a ZIP folder. 

To zip one file: 

| Command | Example |
| ------- | ------- |
| zip ZIPFILE FILE | zip data.zip data.R | 
	
To zip a folder: 

| Command | Example |
| ------- | ------- |
| zip –r ZIPFOLDER FOLDER/ | zip –R datafolder.zip datafolder/ | 

Full documentation can be found here: [https://linux.die.net/man/1/zip](https://linux.die.net/man/1/zip)

## unzip 

The unzip command can be used to extract from common archive formats such as ZIP and RAR.  

To extract all contents to the current directory: 

| Command | Example |
| ------- | ------- |
| unzip FILE | unzip data.zip | 

To only extract all contents to the current directory within a specific subfolder of the archive: 

| Command | Example |
| ------- | ------- |
| unzip FILE FILENOEXTENSION/SUBFOLDER/* | unzip data.zip data/2005/* | 

To extract contents to a specific folder:  

| Command | Example |
| ------- | ------- |
| unzip FILE -d DESTINATION | unzip ziptest.zip -d '/export/home/dor/jharvard' | 

Full documentation can be found here: [https://linux.die.net/man/1/unzip](https://linux.die.net/man/1/unzip)

## gunzip 

gunzip is meant to be used on files ending with .gz or .z.  

To extract a file into the current directory and not save the original compressed file: 

| Command | Example |
| ------- | ------- |
| gunzip FILE | gunzip yourdocument.docx.gz | 

To extract a file into the current directory and keep both the compressed and decompressed file: 

| Command | Example |
| ------- | ------- |
| gunzip < ORIGINALFILE > EXTRACTEDFILE | gunzip < yourdocument.docx.gz > yourdocument.docx | 
 
Full documentation can be found here: [https://linux.die.net/man/1/gunzip](https://linux.die.net/man/1/gunzip) 

 