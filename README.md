# Screenshot Tool with Image Description

## Overview

This project is a GUI application built with PyQt5 that allows users to capture screenshots, generate image thumbnails, and describe the content of the captured images using the Google Gemini API. The application provides customizable settings for various parameters, including screen dimensions, API keys, and model parameters.

## Features

- **Capture Screenshots**: Select an area on the screen to capture and save it as an image.
- **Thumbnail Preview**: Display a thumbnail of the most recent screenshot.
- **Image Description**: Use the Google Gemini API to describe the content of the captured image.
- **Customizable Settings**: Adjust settings such as screen width, height, and model parameters through a settings dialog.

## Installation

1. **Clone the Repository**:
   ```bash
   git clone git@github.com:Rajora0/screenshot-to-description-app.git
   cd screenshot-to-description-app
   ```

2. **Install Dependencies**:
   Make sure you have Python 3.10 installed. Then, install the required libraries using `pip`:
   ```bash
   pip install PyQt5 pillow google-generativeai
   ```

3. **Configure the API Key**:
   Obtain an API key from Google Gemini and configure it in the settings dialog of the application.

## Usage

1. **Run the Application**:
   ```bash
   python main.py
   ```

2. **Interact with the Application**:
   - **Open Settings**: Click on "Settings" in the menu bar to configure screen dimensions, API key, and model parameters.
   - **Capture Screenshot**: Click on "Select Area and Take Screenshot" to select a region on the screen and capture it.
   - **Generate Response Message**: Click on "Generate Response Message" to describe the content of the latest screenshot using the configured model parameters.

## Compiling with PyInstaller

To compile the project into a standalone executable, you can use PyInstaller. Follow these steps:

1. **Install PyInstaller**:
   ```bash
   pip install pyinstaller
   ```

2. **Compile the Project**:
   Run the following command in the project directory:
   ```bash
   pyinstaller --onefile --windowed main.py
   ```

   - `--onefile` bundles everything into a single executable file.
   - `--windowed` prevents a terminal window from appearing (useful for GUI applications).

3. **Find the Executable**:
   After compiling, the executable will be located in the `dist` directory.

## Files

- **`main.py`**: Entry point of the application.
- **`screenshot_app.py`**: Contains the `ScreenshotApp` class, which handles the main functionality of the application.
- **`settings_dialog.py`**: Contains the `SettingsDialog` class for configuring application settings.
- **`gemini_image_describer.py`**: Handles interaction with the Google Gemini API for image description.

## Configuration

Settings are stored in a file named `settings.ini`. You can adjust default settings for screen dimensions, API key, and model parameters in this file.

Example `settings.ini`:

```ini
[General]
screenWidth = 800
screenHeight = 600
apiKey = your_api_key_here
windowX = 100
windowY = 100
windowWidth = 400
windowHeight = 300
```

## Troubleshooting

- **"Image not found"**: Ensure the screenshot is saved correctly and that the file exists in the same directory as the script.
- **API Errors**: Verify your API key and network connection.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgements

- [PyQt5](https://riverbankcomputing.com/software/pyqt/intro)
- [Pillow](https://python-pillow.org/)
- [Google Gemini API](https://ai.google.dev/gemini-api/docs/prompting_with_media)