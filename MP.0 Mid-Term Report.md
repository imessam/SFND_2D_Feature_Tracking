# MP.1 Data Buffer Optimization
- To buffer only 2 images per time, I check first if the size of the buffer vector became 2, if yes, 
then I put the image at the last index (i = 1) into the first index (i = 0), then I add the new image to the last index(i = 1).

# MP.2 Keypoint Detection
- To select any of the detectors from a string, I created an enum to store each detector type,
then I mapped each detector string to its enum value.
- Then I created a switch using each of the enum values, the switch check the enum value
mapped from the input detector type string map[detectorType].
- For the Harris detector, I created a sperate function like ShiTomasi as it's treated differently
from the modern detectors.
- And for the modern detectors I created a single function for all of them as only the value of the
detector is the only difference, but the rest of the code is the same.

# MP.3 Keypoint Removal
- Using the rectangle dimensions of the car to focus on, x_left, y_top, width, height,
I defined four variables xmin = x_left, y_min = y_top, xmax = x_left + width, ymax = y_top + height.
- Then for each of the detected keypoint, I check if x is in the range xmin <= x >= xmax, and
y in the range ymin <= y >= ymax.

# MP.4 Keypoint Descriptors
- To select any of the descriptors from a string, first I used a single function for all the descriptors
, as they follow the same procedure, only the value of the descriptor is the difference.
- Then I created an enum to store each descriptor type, and I mapped each descriptor string to its enum value.
- Then I created a switch using each of the enum values, the switch check the enum value
mapped from the input descriptor type string map[descriptorType].

# MP.5 Descriptor Matching
- To select one of the matchers or the selectors from an input string, I used a single function for the two of them,
then I implemented the FLANN matcher exactly like the one I've implemented in a previous lesson, as well as the KNN selector.


# MP.6 Descriptor Distance Ratio
- To filter pair of keypoints, I set a minimum distance ratio of 0.8.

# MP.7 Performance Evaluation 1
- Please check the csv file detections_num.csv

# MP.8 Performance Evaluation 2
- Please check the csv file matching_num.csv

# MP.9 Performance Evaluation 3
- Please check the csv files detections_time.csv and descriptor_time.csv