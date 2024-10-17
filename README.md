# Intel RealSense Camera-Service
This repository contains a RESTful service designed to interface with an Intel RealSense camera. The service provides a GET /get_snapshot endpoint, which captures a frame from the camera’s colored video stream and returns it as a base64-encoded image. This allows for easy integration of real-time color image data into other applications without needing to handle complex image processing or camera interaction directly.

## Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/kevi-nguyen/intel-realsense-camera.git
   cd intel-realsense-camera
   ```

2. **Install Dependencies**:
   Activate your virtual environment and install the required dependencies from the `requirements.txt` file.
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the Service**:
   To start the button service, use the following command:
   ```bash
   python Camera.py
   ```
   This will start the FastAPI service on `http://0.0.0.0:8083`.

## Build from Source

To use the Intel RealSense camera with this repository, you’ll need the pyrealsense2 Python wrapper. 
You may need to build the librealsense SDK from source to have access to this library.

Take a look at [librealsense](https://github.com/IntelRealSense/librealsense) for a step-by-step guide.

Follow the steps below for MacOS installation:

Prerequisites

1.	Install Homebrew (if not already installed):
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```


2.	Install required dependencies:
   ```bash
   brew install cmake pkg-config libusb boost python@3.9
   brew install glfw
   ```


Steps to Build

1.	Clone the librealsense repository:

   ```bash
   git clone https://github.com/IntelRealSense/librealsense.git
   cd librealsense
   ```

2.	Create a build directory:

   ```bash
   mkdir build && cd build
   ```

3.	Configure the build:
Use cmake to configure the build. Make sure to enable the Python bindings.

   ```bash
   cmake .. -DBUILD_PYTHON_BINDINGS=ON -DPYTHON_EXECUTABLE=$(which python3)
   ```

4.	Build the SDK:

   ```bash
   make -j4
   ```

5.	Install the Python wrapper:
After the build is complete, you can install the pyrealsense2 Python wrapper:

   ```bash
   sudo make install
   ```

Verifying the Installation

To verify that the pyrealsense2 wrapper is correctly installed, open a Python REPL and try importing the library:

   ```bash
   python3
   ```

   ```bash
   import pyrealsense2 as rs
   ```

If the import works without errors, the installation was successful.


