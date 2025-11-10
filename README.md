# OPENING--AND-CLOSING
## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import the necessary packages.


### Step2:
Create the Text using cv2.putText.


### Step3:
Create the structuring element.

### Step4:
Perform opening operation and display the result

### Step5:
Similarly, perform closing operation and display the result

 
## Program:

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Create a blank image
image = np.zeros((500, 500, 3), dtype=np.uint8)
# Add text on the image using cv2.putText
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, 'PRIYADHARSHINI P', (40, 250), font, 1, (255, 255, 255), 2, cv2.LINE_AA)
# Create a simple square kernel (3x3)
kernel = np.ones((3, 3), np.uint8)
# Display the input image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for displaying
plt.title("Input Image with Text")
plt.axis('off')
# Opening is erosion followed by dilation
opened_image = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)
# Display the result of Opening
plt.imshow(cv2.cvtColor(opened_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Opening Operation")
plt.axis('off')
# Closing is dilation followed by erosion
plt.imshow(cv2.cvtColor(opened_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
closed_image = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)
plt.title("Closing Operation")
plt.axis('off')
```
## Output:

### Display the input Image
<img width="386" height="402" alt="image" src="https://github.com/user-attachments/assets/152388da-dce2-42e0-90f1-6264257b1431" />


### Display the result of Opening

<img width="371" height="399" alt="image" src="https://github.com/user-attachments/assets/135354f0-70e6-4902-88f6-87fcafb310ef" />

### Display the result of Closing

<img width="359" height="372" alt="image" src="https://github.com/user-attachments/assets/8ca3bee3-76ca-40eb-8cbe-d587262f1499" />

## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
