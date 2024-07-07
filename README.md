## Road Lane Line Detection System
This project implements a Road Lane Line Detection System designed to enhance road safety by accurately detecting lane markings and providing real-time feedback to drivers. The system processes both images and videos to identify lane lines on the road using computer vision techniques.

## Features
- Real-time Lane Detection: Processes videos in real-time to detect lane lines.
- Color-Based Filtering: Utilizes HSL color space to isolate lane colors (white and yellow).
- Edge Detection: Applies Canny edge detection to highlight lane boundaries.
- Region of Interest Masking: Focuses on the road area where lanes are typically found.
- Hough Transform: Detects lines in the edge-detected image.
- Lane Line Smoothing: Averages detected line segments to create smooth lane lines.
- Robust to Noise: Includes Gaussian blur to reduce image noise.
- Easy Configuration: Adjustable parameters to fine-tune detection accuracy.

## Requirements
- Python 3.x
- OpenCV (`cv2`)
- NumPy
- Matplotlib (for image handling)
- MoviePy (for video handling)
  
## Installation
1. Clone the repository:
    git clone https://github.com/your_username/road-lane-detection.git
    cd road-lane-detection
2. Install the required dependencies:
     pip install -r requirements.txt

## Usage
## Single Image Processing
Here's an example of how to process a single image:

import cv2
import matplotlib.image as mpimg
Load image
image = mpimg.imread('image.jpg')
Process image
processed_image = process_image(image)
## Display processed image

cv2.imshow('Processed Image', processed_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
## Video Processing
Here's an example of how to process a video:

video_path = 'video.mp4'
process_video(video_path)

## Overview
This project implements lane detection in images and videos using Python and OpenCV. Lane detection is a fundamental task in autonomous driving and computer vision applications. The process involves several key steps:

Color Selection in HSL Space
convert_hsl(image): Converts an image to HSL (Hue, Saturation, Lightness) color space.
HSL_color_selection(image): Selects white and yellow colors in the HSL space to identify lane lines.
Image Preprocessing

gray_scale(image): Converts the selected color image to grayscale.
gaussian_blur(image): Applies Gaussian blur to the grayscale image to reduce noise.
canny_edge_detection(image): Detects edges using the Canny edge detection algorithm.
Region of Interest Masking

region_of_interest(image, vertices): Masks out the region of interest (typically the road area) in the image to focus on where lane lines are expected.
Lane Line Detection

hough_lines(image, rho, theta, threshold, min_line_len, max_line_gap): Applies the Hough transform to detect lines in the masked edge-detected image.
average_slope_intercept(lines): Calculates the average slope and intercept for left and right lane lines.
make_line_points(y1, y2, line): Computes the endpoints of a line given its slope and intercept.
Drawing Lane Lines

draw_lane_lines(image, lines): Draws the left and right lane lines on the original image.
Image and Video Processing

process_image(image): Combines all the above steps to process a single image and draw lane lines.
process_video(video_path): Processes each frame of a video to detect and draw lane lines, displaying the result in real-time.

## Example output
![Screenshot (102)](https://github.com/Sravani3690/Road-Lane-Line-Detection-System/assets/174925172/1d1a5665-096a-4a0a-b478-f8aaa43fdffd)

