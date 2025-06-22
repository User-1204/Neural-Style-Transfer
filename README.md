# Neural-Style-Transfer

*COMPANY*: CODTECH IT SOLUTUIONS

*NAME*: MAKWANA SAKSHI M

*INTERN ID*: C0DF93

*DOMAIN*: ARTIFICIAL INTELLIGENCE MARKUP LANGUAGE

*DURATION*: 4 WEEKS

*MENTOR*: NEELA SANTHOSH


# Neural Style Transfer Using TensorFlow Hub
Neural Style Transfer Using TensorFlow Hub: Blend content and style images to create stunning artistic visuals with a pre-trained deep learning model.

## Overview:
This project utilizes Neural Style Transfer (NST) powered by TensorFlow and a pre-trained model from TensorFlow Hub. It creatively merges the content of a source image with the artistic style of another, generating visually striking and unique images.

By employing the Magenta Arbitrary Image Stylization model, this implementation delivers high-quality stylizations while ensuring flexibility and ease of use across both local setups and cloud platforms.

## Features:
* Uses TensorFlow Hub’s **`magenta/arbitrary-image-stylization-v1-256`** pre-trained model
* Automatic image resizing with aspect ratio preservation
* Customizable style blending strength for personalized results
* Saves stylized images in high-quality format
* Compatible with local machines and Google Colab

## How It Works:
1. **Load Pre-trained Model** from TensorFlow Hub
2. **Preprocess Images:** Resize and format content & style images
3. **Apply Style Transfer:** Generate the stylized output
4. **Save & Display:** Output image saved and visualized

## Installation

### Prerequisites:
* Python 3.7+
* TensorFlow 2.x
* TensorFlow Hub
* OpenCV
* Matplotlib
* NumPy
* Pillow

### Setup:
Install dependencies with:

```bash
pip install tensorflow tensorflow-hub opencv-python matplotlib numpy pillow
```

## Usage:

### Running Locally:
1. Place your content and style images in the working directory (default names: `Painting.jpg` and `texture.jpg`).
2. Run the script:

```bash
python neural_transfer.py
```

3. The stylized image will be saved as `generated_img.jpg`.

### Running on Google Colab:
1. Upload your images to the Colab environment.
2. Install packages:

```python
!pip install tensorflow tensorflow-hub opencv-python matplotlib numpy pillow
```

3. Run the script in notebook cells.

## Customization:
Control the **style strength** (0.0 to 1.0) to adjust how much the style influences the output:

```python
style_strength = 0.75
stylized_image = model(tf.constant(content_image), tf.constant(style_image), tf.constant(style_strength))[0]
```
Higher values emphasize style; lower values preserve content.

## Troubleshooting:
**FileNotFoundError:** Confirm your image paths and filenames. Use `os.listdir()` to check files.
**Color distortion:** Use Pillow for saving images to avoid color issues:

```python
from PIL import Image
output_image = (stylized_image[0].numpy() * 255).astype(np.uint8)
Image.fromarray(output_image).save("generated_img.jpg")
```

## Future Improvements:
**Batch Processing:** Add support for processing multiple images automatically.
**Style Mixing:** Combine multiple style images for hybrid effects.
**GUI Application:** Build a user-friendly interface for easier use without coding.
**Mobile Support:** Develop a lightweight version suitable for mobile devices.
**Performance Optimization:** Implement faster model inference and GPU acceleration.
**Parameter Tuning:** Expose more customization options such as content/style weights and resolution control.

## Output:
![Image](https://github.com/user-attachments/assets/b2116c8f-0be4-4a3a-9ba2-646693ae8acc)
