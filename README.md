# Edge detection: Canny-detector


Developed by John F. Canny in 1986, the Canny edge detection is a multi-stage algorithm that detects the edges on a wide range of objects. The algorithm extrapolates useful structural information and because of that, the algorithm is applied in various computer vision tasks. As mentioned before, this is a multi-stage algorithm so let's step into it.

# Process of Canny edge detection algorithm

1)    Apply Gaussian Filter to the image.
2)    Determine the gradient matrix.
3)    Apply NMS ( Non - Maximum Surpression ) 
4)    Apply Double Threshold to detect potential edges
5)    Hysteresis. Connect the weak edges to their strong neighbour.


# 1) Gaussian Blur

Blurs an image using a Gaussian filter. The edge detection algorithm is very sensitive to image noise. As a result, it is essential to filter it in order to prevent detecting false. How do we do that? Simple, by applying a gaussian kernel using the OpenCV library.

    blured_image = cv2.GaussianBlur(image, (3, 3), 0)
  
The first parameter is the image that we want to apply blur on. The second parameter is a tuple that determine the size of the kernel applied. A 3 by 3 gaussian kernel would look like this:

![alt text](https://wikimedia.org/api/rest_v1/media/math/render/svg/c1e0a314554ab3663f129961ebd28fec307e74c4)


# 2) Calculating the intensity gradient of the image


