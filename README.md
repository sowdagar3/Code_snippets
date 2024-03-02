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

