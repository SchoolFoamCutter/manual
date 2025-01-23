# Exceptions
You may encounter several different warnings, errors, and other exceptions while using the program. Here is a list of the most common exceptions, why they were caused, and what to do.


## Warnings

### `DecompressionBombWarning`
This warning can be safely ignored. 

This warning is caused by the Python Imaging Library fork (pillow) trying to prevent potential Denial Of Service (DOS) attacks from unpacking too much data.

The reason this warning is raised is because of the resolution of the converted pdf (over 10k pixels for width and height in testing) is a lot of data to decompress.

[Learn more here](https://pillow.readthedocs.io/en/stable/reference/Image.html#PIL.Image.open)


## Errors

### `<Some variable> is not a valid selection for filepickertype! change in .env`
This error is caused by the selected filepickertype (GUI, CLI) being invalid or blank.

1. To fix this error, open the '.env' file in notepad
  > [!IMPORTANT]
  > Do not edit the values of any of the other variables unless you know what you're doing
2. Find the variable "filePickerTypeEnv" (around line 8)
    * it should look similar to `filePickerTypeEnv = "<Some Value>"`
3. Edit in the quotes (<Some Value\> in the example above) and set it to one of the following
    * `gui` or `1` (uses pop-ups for selection, recommended for beginners)
    * `cli` or `2` (uses terminal for selection, recommended for advanced users)
4. Save and exit

### `Permission denied! Unable to create '<directory>'`
This error is caused by the program being unable to create a directory because of lack of permissions from the user

Troubleshooting steps
* Make sure you have permission to edit files in the directory the program is located in
