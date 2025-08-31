Rescue Pad Assignment and Image Analysis
This script processes images containing colored shapes (casualties) and colored circles (rescue pads) to simulate and visualize the assignment of casualties to the nearest available rescue pad based on defined priorities and pad capacities. It also calculates a "Rescue Ratio" to evaluate the effectiveness of the assignment for each image.

Functionality
Object Detection: Identifies different colored shapes (Triangle, Square, Star) as casualties and colored circles (Blue, Pink, Grey) as rescue pads using HSV color range thresholding and contour analysis.
Shape Classification: Classifies detected shapes by matching their contours against predefined templates.
Casualty Prioritization: Assigns priority scores to casualties based on their shape and color.
Rescue Pad Assignment: Assigns casualties to the closest rescue pad with available capacity, prioritizing casualties in water first, then by their priority score.
Land/Ocean Segmentation: Segments the image into land and ocean areas for visualization.
Visualization: Draws lines connecting assigned casualties to their rescue pads, highlights unassigned casualties, and overlays land/ocean segmentation on the output image.
Output Metrics: Calculates and prints the total number of casualties, unassigned casualties, unique shape-color combinations, assigned casualties per pad, pad priority sums, and a Rescue Ratio for each processed image.
Ranking: Ranks the processed images based on their Rescue Ratio.
How to Use
Prepare your images: Place the images you want to process in a folder named input_images in the same directory as your script. The script currently supports .png and .jpg files.
Run the script: Execute the code cell.
View Results:
Output images with visualizations will be saved to a folder named output_images.
Detailed results for each image (total casualties, unassigned, unique combinations, assignments, pad sums, rescue ratio) will be printed to the console.
A final ranking of images based on their Rescue Ratio will be printed to the console.
Configuration
You can adjust the following parameters within the script:

CASUALTY_SCORES: Modify the priority scores for different shapes.
EMERGENCY_SCORES: Modify the emergency scores for different colors.
PAD_CONFIG: Adjust the capacity and colors of the rescue pads.
COLOR_RANGES: Fine-tune the HSV color ranges for detecting different objects.
Minimum contour area thresholds (if area < 80: continue): Adjust to filter out smaller noise or include smaller objects.
Morphological operation iterations (iterations = 2): Adjust to improve mask quality.
Shape classification thresholds (abs(area / template_area - 1) > 1.0, circularity < 0.65): Adjust for better shape detection accuracy.
Rescue Ratio calculation formula: Modify the formula in the process_image function if needed.
Dependencies
This script requires the following libraries:

opencv-python
numpy
math
glob
os
matplotlib
You can install them using pip
