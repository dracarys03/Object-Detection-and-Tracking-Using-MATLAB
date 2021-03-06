In imaging science, image processing is processing of images using mathematical operations by using
any form of signal processing for which the input is an image, a series of images, or a video, such as a
photograph or video frame; the output of image processing may be either an image or a set of
characteristics or parameters related to the image. In this project we have a live video input coming
from a Logitech webcam where the aim is to identify red-colour present anywhere in that frame and
to show the centroid and boundary of this red-coloured object present in a multi-coloured
background.
The first task is to read the input as object from the webcam and give required values to parameters
like ‘FramesPerTrigger’ as ‘inf’ (infinity). Then we start the video and data is stored for only the just
elapsed 1 second ( 200*5ms) to save memory. Each frame is taken at an interval of 5ms and the first
task which is done on this image is that the black and white parts are subtract from the image using
‘imsubtract’command. Next the ‘medfilt2’ command is used to find the median filtered image in the
3 x 3 neighbourhood of a pixel, and then at a distance of every 0.18 is checked in the binary image .
The actual red colour detection takes place in this line:
‘diff_im=bwareaopen(diff_im,300)’ , where 300 is the threshold given by us for detecting red colour.
The next line is also very important as it finds the connected region of red colour using ‘bwlabel’
command with a specified value of n=8 (default for 2-dimensions).
After this we get information relating to the boundary of the object (red colour) and its centroidal
location (of a rectangle). This information is then sent to the monitor for display by giving the
necessary inputs to ‘plot‘. Different font parameters are given and then the data stored till 200
frames ( 1 second) is cleared using ‘flushdata(vid);’.
  
![z](https://user-images.githubusercontent.com/84719685/176025935-85af188f-f685-4f37-b857-8e68ab38b81f.jpg)
![zz](https://user-images.githubusercontent.com/84719685/176025940-aed5cdab-cd21-4d9f-86ea-acc60041ca1e.jpg)
In this project Matlab code is able to identify the red colour object in front of the camera and
encircle it by a red coloured rectangle and also giving the centroid of the object. It can be used if we
want to replace the red colour object by any other object of our desire. The application of this
project is widely used in modern gaming softwares, the latest and most famous being &#39;Pokemon Go&#39;.
We see that there are many uses in navigation and position indicating in many flight vehicles.
