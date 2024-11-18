# Automate the Google Dinosaur Game

This project is a Python-based automation script to play the Google Dinosaur game using `pyautogui` and `Pillow`. The script detects obstacles (cacti and birds) in the game and simulates key presses (`up` and `down`) to control the dinosaur's movements automatically.

## Features
- **Obstacle Detection**: Identifies obstacles such as birds and cacti by analyzing screen pixels.
- **Automated Controls**: Simulates key presses (`up` to jump and `down` to duck) to avoid collisions.
- **Real-time Gameplay**: Continuously monitors the game and reacts to obstacles dynamically.

## Requirements
- Python 3.x
- Libraries:
  - `pyautogui` (for simulating key presses)
  - `Pillow` (for image processing)

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/Prathamesh326/Automate-the-Google-Dinosaur-Game.git
   ```
2. Navigate to the project directory:
   ```bash
   cd Automate-the-Google-Dinosaur-Game
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage
1. Open the Google Dinosaur game in a browser. You can access it by typing `chrome://dino` in Google Chrome or disconnecting from the internet.
2. Run the script:
   ```bash
   python main.py
   ```
3. Wait for 5 seconds to position the game window.
4. Watch the script play the game automatically!

## How It Works
1. **Screen Capture**: The script captures a grayscale image of the game screen using the `ImageGrab` module.
2. **Collision Detection**: 
   - **Birds**: It scans a specific region of the screen for bird-like obstacles and presses the `down` key if detected.
   - **Cacti**: It scans another region for cactus-like obstacles and presses the `up` key to jump.
3. **Automation**: The `pyautogui` module simulates key presses to control the dinosaur.

## Customization
- You can tweak the coordinates in the `isCollision` function to adjust for different screen resolutions or game speeds.

### Code Snippet: Obstacle Detection
```python
def isCollision(data):
    # Check collision for birds
    for i in range(530, 560):
        for j in range(80, 127):
            if data[i, j] < 171:
                click("down")
                return
    # Check collision for cacti
    for i in range(530, 620):
        for j in range(130, 160):
            if data[i, j] < 100:
                click("up")
                return
    return
```

## Contributing
Feel free to fork the repository and submit pull requests with improvements or bug fixes.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Disclaimer
This script is designed for educational purposes and personal use only. Use it responsibly and avoid violating the terms of service of any platform.
