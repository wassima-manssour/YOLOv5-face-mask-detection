
<h1 align="center">
  <br>
  <a href="https://github.com/wassima-manssour/YOLOv5-face-mask-detection"><img src="https://github.com/wassima-manssour/YOLOv5-face-mask-detection/blob/main/README-face-mask-detection/img.png" alt="Markdownify" width="200"></a>
  <br>
  Face Mask Detection
  <br>
</h1>

<h4 align="center">A Face Mask Detection Using <a href="https://github.com/ultralytics/yolov5" target="_blank">YOLO V5</a>.</h4>

<p align="center">

  <a href="#">
    <img src="https://img.shields.io/badge/python-v3.6+-blue.svg"
         alt="Gitter">
  </a>
  <a href="https://www.linkedin.com/in/wassima-manssour-b48a7018a/">
    <img src="https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555"
         alt="Gitter">
  </a>
  <a href="https://github.com/wassima-manssour/YOLOv5-face-mask-detection/network/members">
    <img src="https://img.shields.io/github/forks/Louis3797/awesome-readme-template" alt="forks" />
  </a>
  <a href="https://github.com/wassima-manssour/YOLOv5-face-mask-detection/stargazers">
    <img src="https://img.shields.io/github/stars/Louis3797/awesome-readme-template" alt="stars" />
  </a>
  <a href="https://github.com/wassima-manssour/YOLOv5-face-mask-detection/issues">
    <img src="https://img.shields.io/github/issues/Louis3797/awesome-readme-template" alt="open issues" />
  </a>
  <!--<a href="https://github.com/Louis3797/awesome-readme-template/blob/master/LICENSE">
    <img src="https://img.shields.io/github/license/Louis3797/awesome-readme-template.svg" alt="license" />
  </a>-->

</p>


<p align="center">
  <a href="#Objective">Objective</a> •
  <a href="#Dataset">Dataset</a> •
  <a href="#How To Use">How To Use</a> •
  <a href="#credits">Credits</a> •
  <a href="#support">Support</a>
</p>

<div align="center"> 
  <img src="https://github.com/wassima-manssour/YOLOv5-face-mask-detection/blob/main/README-face-mask-detection/vid-output.gif" alt="screenshot" width="600" height="350"/>
</div>

<div align="center"> 
  <img src="https://github.com/wassima-manssour/YOLOv5-face-mask-detection/blob/main/README-face-mask-detection/face-mask.jpg" alt="screenshot" />
</div>

## Objective
<div>
In this project we will train a custom dataset (wearing mask dataset from roboflow) with YOLOv5 in colab. The input is an image or a video, and the output is the detection wearing a mask or not. 
<br>In next project we will try it for a real time detection.
</div>
<br>

> **Note**
> We used [Google Collaboratory](https://colab.research.google.com/) for the implementation.


## Dataset

The [dataset](https://public.roboflow.com/object-detection/mask-wearing) used in this project is from [roboflow](https://roboflow.com/).You can download it from the official website or from the [repo](https://github.com/wassima-manssour/YOLOv5-face-mask-detection/blob/main/MaskWearing.zip).

<div align="center"> 
  <img src="https://github.com/wassima-manssour/YOLOv5-face-mask-detection/blob/main/README-face-mask-detection/datset.png" alt="screenshot" />
</div>

## How To Use

### :house: Set up the wokplace
- Add the daatset to google colab
<div align="center"> 
  <img src="https://github.com/wassima-manssour/YOLOv5-face-mask-detection/blob/main/README-face-mask-detection/add-data1.jpg" alt="screenshot" />
</div>

- Add the face-mask.yaml file to /yolov5/data/
<div align="center"> 
  <img src="https://github.com/wassima-manssour/YOLOv5-face-mask-detection/blob/main/README-face-mask-detection/add-data2.jpg" alt="screenshot" />
</div>

> **Note**
> If you encounter some problems running the code, check the paths used.



### 🚀&nbsp; implementation
1. Unzip the dataset
```
!unzip -q '/content/MaskWearing.zip'
```

2. Clone the yolov5 repo
```
!git clone https://github.com/ultralytics/yolov5  # clone
```

3. Change your directory to the cloned 
```
%cd yolov5
```

4. Install requirements
```
!pip install -qr requirements.txt  # install
```

5. Train the model
```
!python train.py --img 640 --batch 16 --epochs 100 --data /content/yolov5/data/face-mask.yaml --weights yolov5s.pt --cache
```

6. Display the training image result
```
from IPython.display import Image
Image(filename='/content/yolov5/runs/train/exp/train_batch0.jpg', width=1000)
```

<div align="center"> 
  <img src="https://github.com/wassima-manssour/YOLOv5-face-mask-detection/blob/main/README-face-mask-detection/img4.png" alt="screenshot" />
</div>

7. Detect the mask on a testing image
```
!python detect.py --source /content/test/images/1224331650_g_400-w_g_jpg.rf.483a35a2395bf48e96783587a59fe876.jpg --weights /content/yolov5/runs/train/exp/weights/best.pt --conf 0.35
```

8. Display the output of the detection result
```
Image(filename='/content/yolov5/runs/detect/exp2/1224331650_g_400-w_g_jpg.rf.483a35a2395bf48e96783587a59fe876.jpg', width=1000)
```

<div align="center"> 
  <img src="https://github.com/wassima-manssour/YOLOv5-face-mask-detection/blob/main/README-face-mask-detection/img3.png" alt="screenshot" />
</div>


9. Test the detection model on a video
```
!python detect.py --source /content/video-test.mp4 --weights /content/yolov5/runs/train/exp/weights/best.pt --conf 0.35
```

## Credits

- Emojis are taken from [here](https://github.com/arvida/emoji-cheat-sheet.com)


## Support

<a href="https://www.buymeacoffee.com/manswassimW" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/purple_img.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a>


## You may also like...

- [License Plate Recognition](https://github.com/wassima-manssour/YOLOV7-License-Plate-Recognition) - A License Plate recognition system using YOLO v7, OCR, and theos API.
- [Multiple Chronic Disease Prediction](https://github.com/wassima-manssour/multidiseasepredictionML) - A streamlit web app hosted on Heroku to predicti disease using Machine Learning.

---

> GitHub [@wassima-manssour](https://github.com/wassima-manssour) &nbsp;&middot;&nbsp;
> Linkedin [@wassima-manssour](https://www.linkedin.com/in/wassima-manssour-b48a7018a/)


