# Code_snippets
# To read images from a folder and to plot them
```bash

import os
from PIL import Image
import matplotlib.pyplot as plt


folder_path = "SNGAN"


files = os.listdir(folder_path)

j=0
for i in files:

    image_path = os.path.join(folder_path, i)


    image = Image.open(image_path)


    plt.imshow(image)
    plt.axis('off') 
    plt.show()
    if j==15:
        break
    j+=1

```

# Python script to copy images from one folder to another:
```bash

import shutil
import os

def copy_images(source_directory, destination_directory):
    # Make sure the source directory exists
    if not os.path.exists(source_directory):
        print(f"Source directory '{source_directory}' does not exist.")
        return

    # Make sure the destination directory exists, create it if not
    if not os.path.exists(destination_directory):
        os.makedirs(destination_directory)

    # Get a list of all files in the source directory
    files = os.listdir(source_directory)

    # Filter out only image files (you can customize this based on your image extensions)
    image_files = [file for file in files if file.lower().endswith(('.png', '.jpg', '.jpeg', '.gif', '.bmp'))]

    # Copy each image file to the destination directory
    for image_file in image_files:
        source_path = os.path.join(source_directory, image_file)
        destination_path = os.path.join(destination_directory, image_file)
        shutil.copy2(source_path, destination_path)

# Example usage
source_directory = 'DCGAN3_1_gen_images/'
destination_directory = 'DCGAN3_gen_images'

copy_images(source_directory, destination_directory)
```
