# Video Doorbell, Lab 7

*A lab report by Chris Kruger - crk78*

### In This Report

1. Upload a video of your version of the camera lab to your lab Github repository
1. As usual, update your class Hub repository to add your [forked IDD-Fa18-Lab7](/FAR-Lab/IDD-Fa18-Lab7) repository.
1. Answer the questions in-line below on your README.md.

## Part A. HelloYou from the Raspberry Pi

**a. Link to a video of your HelloYou sketch running.**

<a href="https://youtu.be/pBrssmaRfWo">HelloYou sketch in Action</a>

## Part B. Web Camera

**a. Compare `helloYou/server.js` and `IDD-Fa18-Lab7/pictureServer.js`. What elements had to be added or changed to enable the web camera? (Hint: It might be good to know that there is a UNIX command called `diff` that compares files.)**

Some of the additions that enabled the camera as an input include:
- Adding a picture capture settings variable, such as width/height/quality.
- Creating an instance of `NodeWebcam` using aforementioned settings.
- Adding a `socket.on('takePicture')` function to handle what happens behind the scenes when a picture is taken.
  - This includes creating a unique imagename based on datetime, collecting the actual image data, and emitting the two joined together as an output.

**b. Include a video of your working video doorbell**

<a href="https://youtu.be/ZENb60E6JtA">Video Doorbell in Action</a>

## Part C. Make it your own

**a. Find, install, and try out a node-based library and try to incorporate into your lab. Document your successes and failures (totally okay!) for your writeup. This will help others in class figure out cool new tools and capabilities.**

My original plan to expand on the Video Doorbell concept was to use the package `face-recognition` to place bounding boxes around the faces of people in frame. In practice this was met with many challenges caused by trying to execute on a Rapsberry Pi with javascript. The largest problem was installation of the package itself. The first issue was caused by RPi lacking the package `dlib` which is used for image processing. After manually building it from source on the RPi, `npm install face-recognition` was still failing since it didn't have write access to some root folder. No matter how I tried to change the settings with `sudo` or other permissioning options, I was unsuccessful.
<BR><BR>
Following this I tried to do a much simpler approach of changing the taken picture from color to grayscale. This would at least drive home the core concept of workflows in JS and how `io` works. 

**b. Upload a video of your working modified project**
