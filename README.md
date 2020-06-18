# DWG-PDF-Converter
A project to convert batch convert DWGs to PDFs.

## Project Overview
At Con Edison, there were many times where they received PDF or DWG drawings from contractors, that need to be converted the other version. If a PDF was received, they would need it as a DWG to work on it and edit it. Asking the contractor for DWG version was often a tedious process, and AutoCAD does not support batch conversion. If they wanted to send the drawings to the customer, to convert each file to a PDF was tedious and sometimes wouldn't work in AutoCAD. The name will not be saved the same as the original and the user will have to rename each file with long complex file names based on Con Edison Convention Techniques. To manually convert 1000s of drawings, would in itself be a full time job. The project was to create a program to do this using VBA and AutoCAD API. I created a tool where the user would specify the files or directory of files they would like to process. The program will copy the files or directory to the server, convert them, save the files as their original name, send an email to the user saying the files have been converted with a link to the files/directory. After the drawings have been converted, the files will be deleted after 7 days as set by the admin to avoid overloading the server. The challenge was that it had to be a tool that anyone can access, without having to download on their machine due to the limitations set by Con Edison, where only an admin can download any executables. The solution was to place this program and processed in the background on a server, having a File Listener. The File Listener would listen for any directories added in a certain location, and it will begin the process notifying the user when it is complete. 

## Project Goals

* Fully designed and implemented by me.
* Weekly meetings with manager showing progress for the week.
* Obtaining admin approval to create the executable.
* Obtaining a server to run the program on.
* Obtaining a no-reply email to be used to let user track progress.
* Have the ability to convert PDFs-to-DWGs.
* Have the ability to convert DWGs-to-PDFs.
* Making it as convenient and as quick as possible for the user.
* Client Side:
  * User will specify the file/directory they would like to process.
  * The program can convert a multi-page PDF file.
  * The program can convert a directory of multi-page PDFs.
  * The program can convert a directory of single-page PDFs.
  * The directory will be copied to the server for processing.
  * No additional downloads for the user.
  * The user will receive an email with a link to the processed files.
* Server Side: 
  * There is a File Listener, watching for a new directory.
  * When it sees a new directory, it will open a process of AutoCAD with an Embedded Drawing.
  * The drawings will be converted and stored on the server.
  * An email will be sent to the user with a link to the files.
  * The files will be deleted after 7 days as specified by the admin.

## Skills Used
  
* Software:
  * Visual Studio
  * AutoCAD
  * AutoCAD API

* Languages:
  * VBA
  * C#
