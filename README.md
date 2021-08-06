# OCR in Java

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/from-referrer/)

## _General Info_
Simple OCR project created with Java to read text from image.

## _Installation_ & Environment variables
To create a simple ocr software, download the tesseract library and install it from [github](https://github.com/UB-Mannheim/tesseract/wiki).
You'll then need to install tesseract in a local directory, default path:
```
.\Tesseract-OCR\tessdata
```
You must define `TESSDATA_PREFIX` in your environment variables.

and then install [image magick](https://imagemagick.org/) to make some adjustments to the image, and help tesseract to improve text recognition.
The default path:
```
.\ImageMagick-7.1.0-Q16-HDRI
```
So lets beging by creating a new maven project and add in pom.xml three dependecies. The first for tesseract library, and the 
seconde for creating a pdf document using iText and the last one is for image magick library.

```bash 
 <dependency>
    <groupId>net.sourceforge.tess4j</groupId>
    <artifactId>tess4j</artifactId>
    <version>4.5.4</version>
 </dependency>
```
```bash 
 <dependency>
    <groupId>com.itextpdf</groupId>
    <artifactId>itextpdf</artifactId>
    <version>5.5.13.2 </version>
 </dependency>
```
```bash 
 <dependency>
       <groupId>org.im4java</groupId>
       <artifactId>im4java</artifactId>
       <version>1.4.0</version>
 </dependency> 
```
## _About the code_
The source code is written in 6 classes:
```
  - src
   |
   - main
    |
    - java
     |
     - ocr
      |     
      - Main.java
      - ImgProcess.java
      - Imgtext.java
      - TextPdf.java
      - getTesseractCmd.java
      - MyRunnable.java
    - resources
     |
     - images
      - ...
```

#
The code is relatively simple, we first open picture in which we are interested in. and we use some digital image processing:
 -Increase contrast and removing black border around the image that may have during scanning.
 -Deskew: (rotation of the image) This means deskewing the image, to bring it in the right format and right shape..
 -Binarize image: means to convert a colored image into a black and white.
#
 After that we jump to Imgtext.java class, we are creating a new instance of tesseract. we indicate where we have installed
 the library and then we do a text recognition using the doOCR() method.
#
 And then add this text to Pdf document created from scratch based on iText.

#
The last thing left is creating a searchable pdf with invisible text layer place on the top of the image.


 

 









