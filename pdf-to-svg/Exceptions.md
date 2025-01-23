# Exceptions
You may encounter several different warnings, errors, and other exceptions while using the program. Here is a list of the most common exceptions, why they were caused, and what to do.


### `DecompressionBombWarning`
This warning can be safely ignored. 

This warning is caused by the Python Imaging Library fork (pillow) trying to prevent potential Denial Of Service (DOS) attacks from unpacking too much data.

The reason this warning is raised is because of the resolution of the converted pdf (over 10k pixels for width and height in testing) is a lot of data to decompress.

[Learn more here](https://pillow.readthedocs.io/en/stable/reference/Image.html#PIL.Image.open)