## Code Summary: Frequency Domain Filtering and Noise Removal

### Overview
This project demonstrates frequency domain filtering and noise removal using Python and OpenCV. It includes applying various filters (Ideal, Gaussian, Butterworth), creating hybrid images, and removing noise from grayscale images.

### Key Functions

- **`ideal_filter()`**: Creates Ideal Low-Pass Filter (LPF) or High-Pass Filter (HPF) masks.
- **`gaussian_filter()`**: Generates Gaussian LPF or HPF masks.
- **`butterworth_filter()`**: Produces Butterworth LPF or HPF masks.
- **`apply_filter()`**: Applies a selected filter to an image and returns magnitude spectra and filtered image.
- **`create_hybrid_image()`**: Combines low-frequency components of one image with high-frequency components of another.
- **`remove_noise()`**: Removes noise from an image by manipulating frequency components and reconstructing the image.

### Interactive Filtering
- Uses IPyWidgets to upload images, select filter types, adjust cutoff frequencies, and set filter parameters. Displays real-time results.

### Example Usage

**Applying Filters:**
```python
image = cv2.imread('example_image.jpg', cv2.IMREAD_GRAYSCALE)
magnitude_spectrum, filter_mask, filtered_magnitude_spectrum, filtered_image = apply_filter(
    image, butterworth_filter, cutoff=20, filter_type='lpf', order=2)
```

**Creating Hybrid Image:**
```python
hybrid_image = create_hybrid_image(image1, image2, cutoff_low=20, cutoff_high=20)
cv2.imwrite('hybrid_image.png', hybrid_image)
```

**Removing Noise:**
```python
remove_noise(img, output_prefix='output_image')
```

### Saving and Visualization
- Processed images and results are saved and displayed using `cv2.imwrite` and `matplotlib.pyplot`.

