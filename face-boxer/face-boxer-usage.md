This __face-boxer.py__ script is more-or-less the same code that you'll find in the OpenCV tutorial: [Face Detection using Haar Cascades](http://docs.opencv.org/trunk/doc/py_tutorials/py_objdetect/py_face_detection/py_face_detection.html). For another variation, with more explanation, check out [RealPython's tutorial](https://realpython.com/blog/python/face-recognition-with-python/). 



## Usage

The `face-boxer.py` script is designed to be run from the command-line. It has __two__ required arugments:

1. The path to a XML file containing a [Haar-cascade](http://en.wikipedia.org/wiki/Haar-like_features) of visual features. In this example, it will be the [features that make up a face](http://docs.opencv.org/trunk/_images/haar.png).
2. The path to an image file that you want to perform face-detection on. You can pass in more than one image file as space-separated arguments.

The `face-boxer.py` script will then read each image file and perform this routine: For every detected object in a given image, the object is highlighted in a light-blue box, and this altered image is __saved__ to:

       /path/to/the-original-image--faces.jpg



### Installation

If you are a Stanford student taking [CompCiv](http://compciv.org), you should be able to copy the `face-boxer.py` script and follow the instructions without a problem on __corn.stanford.edu__. The script has been tested on Python 2.7.8 and OpenCV 2.4x


### Download the haar cascade file

You'll need the XML file that contains the data necessary for OpenCV to do its work. The file below contains the pattern data for frontal-aspects of a face:

```sh
curl -so haarcascade_frontalface_default.xml http://stash.compciv.org/opencv/haarcascades/haarcascade_frontalface_default.xml
```
If detecting faces is boring to you, you can [download a zipped archive of all the Haar-cascade files from here](http://stash.compciv.org.s3.amazonaws.com/opencv/haarcascades.zip), which is simply a mirror of [what's in the OpenCV repo](https://github.com/Itseez/opencv/tree/master/data/haarcascades). Object patterns include: eyes, eyes with glasses, full (human) bodies, lower bodies, license plates, smiles, and cat faces.



### Download the photos

```sh
# Download some images
curl -so obama-phone.jpg https://farm9.staticflickr.com/8604/15891607122_794b16aff7_z_d.jpg
curl -so obama-3d.jpg https://farm5.staticflickr.com/4054/4291192697_2ba403a502_b_d.jpg
```
### Call the script

```sh
python face-boxer.py haarcascade_frontalface_default.xml obama-phone.jpg obama-3d.jpg
```

### Out-of-the-box results

(needs some tweaking obviously)

![img](http://web.stanford.edu/~dun/test/obama-phone.jpg-faces.jpg)

![img](http://web.stanford.edu/~dun/test/obama-3d.jpg-faces.jpg)


### With a webcam

If you're interested in seeing the face-detection code work via your own webcam, check [out this RealPython tutorial](https://realpython.com/blog/python/face-detection-in-python-using-a-webcam/). Using your own webcam means you have to have Python and OpenCV installed on your own computer -- [Mac users, check out this tutorial](https://jjyap.wordpress.com/2014/05/24/installing-opencv-2-4-9-on-mac-osx-with-python-support/)