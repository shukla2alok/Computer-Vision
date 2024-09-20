# Hand Gesture Recognition and Control

This project implements hand gesture recognition using OpenCV and allows users to control keyboard actions like jumping in games or navigating using 'WASD' keys based on detected hand gestures.

## Problem Solved

The project provides a hands-free way of controlling games or applications by recognizing hand gestures captured from a live camera feed. This can be used in situations where traditional keyboard input is not ideal.

## How It Works

1. **Camera Input:** The project uses your webcam to capture a live video feed.
2. **Hand Detection:** A portion of the video frame is processed to detect hand gestures.
   - Gaussian blur and HSV color-space conversion are applied to isolate the hand.
   - Morphological transformations are used to reduce noise.
   - Convex hull and convexity defects are used to detect finger tips and measure angles between fingers.
3. **Gesture Recognition:** Based on the number of convexity defects (finger gaps), specific keyboard actions are triggered:
   - **Jump:** When 5 fingers are detected (4 defects).
   - **WASD keys:** For controlling movement in racing games (commented out in the code).
4. **Key Press Simulation:** The pyautogui library is used to simulate keyboard inputs such as pressing the spacebar or WASD keys based on detected hand gestures.

## Setup and Installation

1. Clone the repository:
    ```bash
    git clone <repository-link>
    cd <repository-folder>
    ```

2. Install required dependencies:
    ```bash
    pip install numpy opencv-python pyautogui
    ```

3. Run the script:
    ```bash
    python gesture_control.py
    ```

## Usage

- Make sure your camera is active.
- Position your hand inside the green rectangle on the screen.
- Use different hand gestures (open palm, 1–4 fingers) to trigger the associated keyboard actions.

## Key Mappings

- **Jump:** Open palm (5 fingers).
- **Other Gestures:** WASD keys (uncomment code to use in racing games).

