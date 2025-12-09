# Color Blindness Visualization

This Python script simulates different types of color blindness on an image. It provides a command-line interface to transform an input image to how it might be perceived by individuals with protanopia, deuteranopia, or tritanopia.

## Description

The script converts an image's RGB color space to the LMS (Long, Medium, Short) cone space, which models the response of the three types of cones in the human eye. It then applies a transformation matrix to simulate a specific type of color blindness and converts the image back to the RGB color space.

The supported types of color blindness are:
- **Protanopia:** Inability to perceive red light.
- **Deuteranopia:** Inability to perceive green light.
- **Tritanopia:** Inability to perceive blue light.

## Dependencies

The script requires the following Python libraries:

- **NumPy:** For numerical operations and matrix calculations.
- **Pillow (PIL Fork):** For image manipulation.

## Installation

1.  **Clone the repository (or download the script).**

2.  **Install the dependencies using pip:**

    ```bash
    pip install numpy pillow
    ```

## Usage

The script is run from the command line and accepts three arguments:

```
python main.py <input_image> <output_image> <blindness_type>
```

### Arguments

-   `input_image`: The path to the input image file (e.g., `image.jpg`).
-   `output_image`: The path to save the simulated output image (e.g., `protanopia_image.jpg`).
-   `blindness_type`: The type of color blindness to simulate. Must be one of:
    -   `protanopia`
    -   `deuteranopia`
    -   `tritanopia`

### Example

To simulate protanopia on an image named `image.jpg` and save the result as `protanopia_image.jpg`:

```bash
python main.py image.jpg protanopia_image.jpg protanopia
```

## How It Works

1.  **Load Image:** The input image is loaded and converted to RGB format.
2.  **RGB to LMS:** The RGB pixel values are converted to the LMS color space using a standard conversion matrix.
3.  **Simulation:** A specific color blindness simulation matrix (for protanopia, deuteranopia, or tritanopia) is applied to the LMS pixel values.
4.  **LMS to RGB:** The simulated LMS values are converted back to the RGB color space.
5.  **Save Image:** The final RGB pixel values are used to create and save the output image.

The color transformation matrices used in this script are based on the research available at [daltonize.org](http://www.daltonize.org/).
