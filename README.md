# Parking Space Counter

A computer vision application that counts available parking spaces in a video feed using machine learning.

## Description

This project uses computer vision and machine learning techniques to detect and count available parking spaces in a video feed. It processes video frames, identifies parking spots using a mask, and classifies each spot as empty or occupied using a pre-trained machine learning model.

## Features

- Real-time detection of available parking spaces
- Visual representation of empty and occupied spots
- Counter displaying the number of available spots
- Efficient processing using frame skipping

## Installation

1. Clone the repository:
   ```
   git clone https://github.com/yourusername/parking_space_counter.git
   cd parking_space_counter
   ```

2. Create a virtual environment (optional but recommended):
   ```
   python -m venv venv
   venv\Scripts\activate  # On Windows
   ```

3. Install the required dependencies:
   ```
   pip install -r requirements.txt
   ```

## Usage

1. Ensure you have a video file of a parking lot in the `data` directory.
2. Make sure you have a mask file (`mask_1920_1080.png`) that defines the parking spaces.
3. Run the main script:
   ```
   python main.py
   ```
4. Press 'q' to exit the application.

## Project Structure

- `main.py`: The main script that processes the video and displays the results
- `util.py`: Utility functions for detecting parking spots and classifying them
- `model/model.p`: Pre-trained machine learning model for classifying parking spots
- `mask_1920_1080.png`: Mask file defining the parking spaces
- `data/`: Directory containing video files
- `clf-data/`: Training data for the classifier, divided into empty and not_empty categories

## Dependencies

- OpenCV (opencv-python): For computer vision tasks
- scikit-learn: For machine learning functionality
- pandas: For data manipulation
- Pillow: For image processing
- scikit-image: For image processing algorithms
- matplotlib: For visualization

## How It Works

1. The application reads a video file and a mask file that defines the parking spaces.
2. It uses connected components analysis to identify individual parking spots.
3. For each frame (at specified intervals), it extracts each parking spot and classifies it as empty or occupied using a pre-trained machine learning model.
4. The application displays the video with rectangles around each parking spot (green for empty, red for occupied) and shows the count of available spots.
5. To optimize performance, the application only processes frames at specified intervals and uses a difference-based approach to prioritize spots that might have changed.
