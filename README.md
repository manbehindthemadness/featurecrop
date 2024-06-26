
---

# FeatureCrop

FeatureCrop is a Python library designed to automatically crop an image to the innermost closed contour containing the most feature data. It is particularly useful for applications where the focus is on extracting important features from an image while removing unnecessary background.

## Installation

You can install FeatureCrop via pip:

```bash
pip install featurecrop
```

## Usage

![image](https://github.com/manbehindthemadness/featurecrop/assets/24589462/54ca51bf-b24d-4f62-b102-68c9a550578e)

### Basic Usage

```python
from featurecrop import featurecrop
import cv2

# Load your image
image = cv2.imread('your_image.jpg')

# Perform autocropping
cropped_image = featurecrop.autocrop(image)

# Use the cropped image for further processing or display
cv2.imshow('Cropped Image', cropped_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### Options

You can also visualize the contours detected during the cropping process by setting the `show_contours` parameter to `True`:

```python
cropped_image = featurecrop.autocrop(image, show_contours=True)
```

## How it Works

1. **Preprocessing**: The input image is converted to grayscale and a Laplacian filter is applied to detect edges.
2. **Contour Detection**: Contours are detected using OpenCV's contour detection functions.
3. **Contour Analysis**: Closed contours are identified and analyzed based on their hierarchy and area.
4. **Cropping**: The innermost closed contour containing the most feature data is identified and used to crop the image.

## Contributing

Contributions are welcome! If you encounter any issues or have suggestions for improvements, please feel free to open an issue or submit a pull request on [GitHub](https://github.com/manbehindthemadness/featurecrop).

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.

---
