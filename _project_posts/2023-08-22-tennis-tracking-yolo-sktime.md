---
layout: project_post
title:  "Tennis Tracking with YOLO and Sktime"
summary: "Learn how to track tennis ball movements and detect bounce points using YOLO and machine learning techniques."
author: arnav
date: '2023-08-22'
category: ['AI', 'Computer Vision', 'Tracking']
tags: yolo, sktime, python, tennis_tracking
thumbnail: /assets/img/posts/tennis_tracking_logo.png"
keywords: tennis tracking, yolo, sktime, python, machine learning, video prediction
usemathjax: false
permalink: /project/tennis-tracking-yolo-sktime/
---

# Tennis Tracking with YOLO and Sktime

This project showcases how to track tennis ball movements using YOLO and detect bounce points using Sktime's TimeSeriesForestClassifier. The project is set up to run on both local machines and Google Colaboratory with GPU support.

## How to Run

### Prerequisites:
- Compatible **GPU** to install TensorFlow, or use [Google Colaboratory](https://colab.research.google.com/notebooks/) with **Runtime Type** set to **GPU**.

### Steps:

1. **Clone the repository:**

   ```bash
   git clone https://github.com/unforgettablexD/tennis_tracking.git
   ```

2. **Download YOLOv3 weights:**  
   Download the weights (237 MB) from [here](https://pjreddie.com/media/files/yolov3.weights) and add them to the [Yolov3 folder](https://github.com/unforgettablexD/tennis_tracking/tree/main/Yolov3).

3. **Install dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

4. **Run the prediction command:**

   ```bash
   python3 predict_video.py --input_video_path=VideoInput/video_input3.mp4 --output_video_path=VideoOutput/video_output.mp4 --minimap=0 --bounce=0
   ```

5. **Running in Google Colaboratory:**  
   Upload all the files, including the YOLOv3 weights, to your Google Drive.

6. **Set up Google Colab:**

   - Create a Colab notebook in the same directory as `predict_video.py`
   - Change **Runtime Type** to **GPU**
   - Connect Google Drive:

   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   ```

7. **Change working directory in Colab:**

   ```python
   import os
   os.chdir('drive/MyDrive/Colab Notebooks/tennis-tracking')
   ```

8. **Install specific requirements for Colab (other dependencies are pre-installed):**

   ```python
   !pip install filterpy sktime
   ```

9. **Run the `predict_video.py` script:**

   ```bash
   !python3 predict_video.py --input_video_path=VideoInput/video_input3.mp4 --output_video_path=VideoOutput/video_output.mp4 --minimap=0 --bounce=0
   ```

### Video Output:

Once the script completes, the video will be saved in the [VideoOutput folder](https://github.com/unforgettablexD/tennis_tracking/tree/main/VideoOutput). If `--minimap` is set to `1`, the output will include a game video, a minimap video, and a combined video.


**Minimap Disabled (`--minimap=0`)**           |  **Minimap Enabled (`--minimap=1`)**
:-------------------------:|:-------------------------:
![input_img1](https://raw.githubusercontent.com/unforgettablexD/tennis_tracking/main/VideoOutput/input6.gif)  |  ![output_img1](https://raw.githubusercontent.com/unforgettablexD/tennis_tracking/main/VideoOutput/input3.gif)


## Bounce Detection

This project uses the machine learning library [Sktime](https://www.sktime.org/en/stable/index.html) to predict tennis ball bounce points. Specifically, the `TimeSeriesForestClassifier` was trained on 3 variables: `x`, `y` coordinates of the ball, and its velocity `V` (`V2-V1/t2-t1`). You can view the training data [here](https://github.com/unforgettablexD/tennis_tracking/blob/main/bigDF.csv).

To enable bounce detection, use the `--bounce=1` flag. When this option is active, bounce points will be detected and displayed on the video.

**Example of Bounce Detection (`--bounce=1`)**:  
<p align="center">
  <kbd>
    <img width=500 src="https://raw.githubusercontent.com/unforgettablexD/tennis_tracking/main/VideoOutput/9bounces.gif">
  </kbd>
</p>


### Model Performance:

The model achieves an accuracy of **98%** for true negatives (non-bounces) and **83%** for true positives (bounces).

## Conclusion

This tennis tracking project combines YOLO for ball detection and Sktime for bounce prediction. The ability to detect ball movement and predict bounce points can have applications in sports analytics and video analysis. If you have any issues or questions, feel free to open a new [Issue](https://github.com/unforgettablexD/tennis_tracking/issues) on GitHub.
```