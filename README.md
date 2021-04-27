
## Description

This repository represents open-source detection methods with YOLOv5 at the edge (on camera), sending cloud storage and importing data.
YOLO model trains on the COCO dataset and can detect up to 80 classes.
With the help of this model, I detect objects on video frames and save the bounding boxes conditions in a text file, send them to the CORTX cloud, and store them there.

The left top gif is the original film.\
The right top gif is the yolo detection output.\
The center down gif is the output after import the data from the cloud.

<p align="center">
   <img src="./gif/original.gif">
   <img src="./gif/yoloResults.gif">
   <img src="./gif/outputAfterReceive.gif">
</p>

## Requirements

Python 3.8 or later with all [requirements.txt](https://github.com/ultralytics/yolov5/blob/master/requirements.txt) dependencies installed, including `torch>=1.7`. To install run:
```bash
$ pip install -r requirements.txt
```

## Inference

`detectAndSend.py` runs inference, downloading models automatically from the [latest YOLOv5 release](https://github.com/ultralytics/yolov5/releases) and saving results to `runs/detect`.

```bash
$ python detectAndSend.py --source 0  # webcam
                            file.jpg  # image 
                            file.mp4  # video
                            path/  # directory
                            path/*.jpg  # glob
                            'https://youtu.be/NUsoVlDFqZg'  # YouTube video
                            'rtsp://example.com/media.mp4'  # RTSP, RTMP, HTTP stream
```

```bash
$ python detectAndSend.py  --source test.mp4 --weights yolov5s.pt --conf 0.25 --save-txt
```

## Future work


