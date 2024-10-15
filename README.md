# Intel RealSense Camera-Service
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
