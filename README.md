# ParkSpot Monitoring System

## Introduction
Welcome to the ParkSpot Monitoring System - an innovative solution designed to revolutionize the way parking spaces are monitored. Utilizing the latest in Computer vision technology and real-time data analytics, ParkSpot provides accurate, up-to-the-minute availability information for parking lots. This system is designed to help drivers find parking spaces more efficiently, reduce traffic congestion, and optimize parking space utilization.


## Getting Started

### Prerequisites
- An environment capable of running Python 3.12+

### Installation
1. Clone the repository to your local machine:
```
git clone https://github.com/harshilmalhotra/ParkSpot-Monitoring-System.git

```
2. Navigate to the cloned directory:
```
cd ParkSpot-Monitoring-System

```
3. Install the required dependencies:
```
pip install -r requirements.txt

```

4. Run the application
```
python main.py

```

## Working
In this project I have used OpenCV (cv2) to analyze a video of a car park with the goal of counting the number of available parking spaces. Here's a breakdown of what the code does:

1. It opens a video file named 'carPark.mp4' for processing or you can use live video feed from CCTV camera.

2. The `checkParkingSpace` function is defined, which takes an image (a frame from the video) as input.

3. For each position in `posList`, it crops the image to a rectangle of a certain width and height starting at the position (x, y).

4. It converts each frame to grayscale, applies a Gaussian blur, and then applies an adaptive threshold to create a binary image. It then applies a median blur and dilation to reduce noise.
5. It counts the number of non-zero pixels in the cropped image. This count is likely used as a simple measure of whether a car is present in the parking space. The threshold of 750 is likely determined empirically.
6. If the count is less than 750, it assumes the parking space is empty, increments a counter of empty spaces, and sets the color to green. Otherwise, it sets the color to red.
7. If you want to integrate an external device to show the output, then you can send the value of `spaceCounter` variable to the device to display empty spaces.

## Screenshots
![Screenshot 2024-04-02 141957](https://github.com/Harshilmalhotra/ParkSpot-Monitoring-System/assets/111488708/9bcfcb99-4554-4f34-9c74-d839e15d6afe)

https://github.com/Harshilmalhotra/ParkSpot-Monitoring-System/assets/111488708/5d9390aa-3a67-4059-8aa6-7a52b1226dbf

### Contributing
We welcome contributions to the ParkSpot Monitoring System! If you have a suggestion that could make this project better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".

### Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (git checkout -b feature/<featurename>)
3. Commit your Changes (git commit -m 'Added <featurename> feature')
4. Push to the Branch (git push origin feature/<featurename>)
5. Open a Pull Request