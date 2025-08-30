**Real-Time Object Measurement Using OpenCV**
This project implements a real-time system to measure the physical dimensions (width and height in centimeters) of objects using a standard webcam. It leverages computer vision techniques from the OpenCV library, utilizing an ArUco marker for scale reference and advanced algorithms like Canny Edge Detection and contour analysis for precise measurement.

**Table of Contents**
Features

How It Works

Project Structure

Prerequisites

Installation & Setup

Usage

Results

Testing

Future Scope

Contributing

License

Acknowledgements

**Features**
Real-Time Measurement: Accurately measures object dimensions from a live webcam feed.

ArUco Marker Calibration: Uses a predefined 5x5 ArUco marker for automatic pixel-to-centimeter conversion, eliminating complex manual camera calibration.

Robust Detection: Employs Canny Edge Detection and contour analysis to handle various object shapes and low-resolution inputs.

Multi-Object Support: Can detect and measure multiple objects within the same frame.

User-Friendly Output: Displays measurements directly overlaid on the live video stream.

**How It Works**
Video Acquisition: Captures frames from a connected webcam.

ArUco Marker Detection: Identifies a 5x5 ArUco marker in the frame to calculate a pixels-to-centimeters conversion ratio based on its known physical size (5cm x 5cm).

Object Detection: Preprocesses the image (grayscale conversion, adaptive thresholding) and extracts contours of objects present.

Measurement: For each detected object, a minimum area rotated rectangle is fitted. The pixel dimensions of this rectangle are converted to real-world centimeters using the ratio from the ArUco marker.

Output: The dimensions (width and height) are drawn directly onto the video frame, which is displayed to the user in real-time.

**Project Structure**

Real-Time-Object-Measurement/
│
├── measure_object_size.py          # Script to measure objects in a static image
├── measure_object_size_camera.py   # Main script for real-time measurement via webcam
├── object_detector.py              # Custom class for object detection logic
├── requirements.txt                # Python dependencies (see below)
├── phone_aruco_marker.jpg          # Example image for testing
└── README.md
**Prerequisites**
Python: 3.8 or higher

Operating System: Windows 10/11, Linux, or macOS

Hardware:

Processor: Intel i5 or equivalent

RAM: 4GB or more

Webcam

Installation & Setup
Clone the Repository:
git clone <your-repository-url>
cd Real-Time-Object-Measurement
Create a Virtual Environment (Recommended):


python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
Install Dependencies:
Install the required libraries using pip and the provided requirements.txt:


pip install -r requirements.txt
If you don't have a requirements.txt, run:


pip install opencv-contrib-python numpy
Usage
Prepare Your Scene:

Print a 5x5 ArUco marker (find one online or generate it using OpenCV tools). The marker must be a perfect square of known size (e.g., 5x5 cm).

Place the object you want to measure next to the ArUco marker in the camera's view.

Run the Real-Time Measurement Script:


python measure_object_size_camera.py
This will open a window showing your webcam feed.

Using the System:

Ensure the ArUco marker is clearly visible in the frame.

The system will automatically detect the marker and any other objects, displaying their width and height in centimeters.

Press the ESC key to exit the application.

Test with a Static Image (Optional):
Place an image file (e.g., phone_aruco_marker.jpg) in the project directory and run:


python measure_object_size.py
**Results**
The system outputs the measurements directly on the video stream. Examples from the project report include measurements of a smartphone, remote control, card box, and other common objects, demonstrating accuracy within an expected margin of error.

https://media/image18.jpeg
Example output showing measurements in centimeters.

**Testing**
The system was validated against various test cases to ensure functionality and accuracy. Key test scenarios included:

Measuring single objects.

Measuring multiple objects simultaneously.

Handling scenarios where the ArUco marker is missing.

For detailed test cases and results, refer to Section 6 of the project report.

**Future Scope**
3D Volumetric Measurement: Extend the system to calculate object volume.

Advanced ML Models: Integrate deep learning models (e.g., YOLO, SSD) for more robust object detection and classification.

Cloud Integration & Database: Save measurement history to a cloud database for tracking and analytics.

Enhanced UI: Develop a graphical user interface (GUI) with features like saving results, taking snapshots, and adjusting settings.

Improved Calibration: Implement automatic calibration without the need for a physical marker.

**Contributing**
Contributions are welcome! Please feel free to fork the repository, make changes, and submit pull requests. For major changes, please open an issue first to discuss what you would like to change.

**License**
This project is licensed for academic and research purposes. Please ensure proper attribution if you use this code.

**Acknowledgements**
This project was developed by Bhoompally Keerthi (22911A1278) under the guidance of Mr. B. Srinivasulu, Associate Professor, Department of Information Technology, Vidya Jyothi Institute of Technology, Hyderabad.

Special thanks to the faculty of VJIT and the open-source community for providing the invaluable tools and libraries that made this project possible.
