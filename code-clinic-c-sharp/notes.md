# [Code Clinic: C#](https://www.lynda.com/C-tutorials/Code-Clinic-C/161815-2.html)

## Problem One: Statistical Analysis

+ Problem:
  + Extract data from RESTful web service
  + Compute statistics on that data
  + Balance the need to avoid swamping the web service without duplicating all of it's data
+ Solution:
  + Build a cache
  + Seed the cache
  + Compute statistics on cache, while filling cache as needed
+ No particularly intersting C# insights

## Problem Two: Image Analysis

+ Problem:
  + Given two images
  + Determine if one of the images is a cropped solution of another image
+ Solution:
  + Assumption: crop only. No other pixel modifications.
  + Convert image to bitmap
  + Check if larger bitmap contains any peices from the smaller bitmap
+ Second Solution:
  + Use library that has image recognition.
  + Allows the detection of images with transformations other than just crop (e.g., scale).
+ Again, no particularly interesting C# insights. I'm actually not sure why this lecture is on
Lynda's [C# learning path](https://www.lynda.com/learning-paths/Developer/become-a-c-developer).

## Problem Three: Eight Queens

+ Apparently this is a classic Computer Science interview question
+ Problem:
  + Set up a chessboard with 8 queens, none of which can attack each other.
  + Find all such possible set-ups.
+ Solution:
  + Take an algorithm someone has already invented (backtracking)
  + Implement it
+ Backtracking:
  + Start with first queen.
  + Recursively place the other queens based on possible conflicts.

## Problem Four: Accessing Peripherals

+ Problem:
  + Work with peripherals.
  + Use mouse movements to create musical sounds.
+ Solution:
  + Most basic: use systems sounds through console (didn't know this was a possibility)
  + Second:
    + Use media player to play sound
    + Control play/pause and volume but not pitch
  + Third, use third-party library to generate sound

## Problem Five: Recursion

+ Problem:
  + Go through a set of directories
  + Extract all images and associated EXIF data
+ Solution:
  + C# has File I/O so iterating through directories and subdirectories is easy
  + Then, use third-party library for extracting EXIF data

## Problem Six: Building the Web

+ Problem:
  + Preformatted HTML templates
  + Insert data portions in the appropriate places in the templates
+ Solution:
  + ASP.NET web forms
  + Read and parse CSV data to get data
  + ASP.NET handles templating

## Takeaways
  
  + You can build things in C#
  + This course was not very valuable to me.
  + Next Steps:
    + Finish up this C# learning path
    + Start targeting more specifics areas of C# that I'm not that familiar with (for example, LINQ)
