# Exceptions
You may encounter several different warnings, errors, and other exceptions while using the program. Here is a list of the most common exceptions, why they were caused, and what to do.


## Warnings
### `Debug Mode Enabled`
Debugging is enabled, shows debug info to the console/terminal in green. This shows more information about how the program works but does not serve any real benefit for the average user. Disable in .env

1. To fix this, open the '.env' file in notepad
  > [!IMPORTANT]
  > Do not edit the values of any of the other variables unless you know what you're doing
2. Find the variable "deathDebug" (around line 6)
    * it should look similar to `deathDebug = "show"`
3. Edit the text in the quotes from "show" to "hide"
4. Save and exit

### `using subfolders is untested`
This warning (only available in cli mode) warns that while you can use subdirectories to choose files, it's untested and may result in buggy behabior

### `Directory <directory path> already exists! skipping!`
This warning is only viewable in debug mode, skips the temporary or output directories if they already exist to prevent an error

### `DecompressionBombWarning`
This warning can be safely ignored. 

This warning is caused by the Python Imaging Library fork (pillow) trying to prevent potential Denial Of Service (DOS) attacks from unpacking too much data.

The reason this warning is raised is because of the resolution of the converted pdf (over 10k pixels for width and height in testing) is a lot of data to decompress.

[Learn more here](https://pillow.readthedocs.io/en/stable/reference/Image.html#PIL.Image.open)


## Errors

### `Please select a valid page`
This error is caused by selecting a page that does not exist or it cannot find the page file. Double check the page number you entered and try again

### `Please select a number`
THis error is caused by not entering a number

### `<Some variable> is not a valid selection for filepickertype! change in .env`
This error is caused by the selected filepickertype (GUI, CLI) being invalid or blank.

1. To fix this error, open the '.env' file in notepad
  > [!IMPORTANT]
  > Do not edit the values of any of the other variables unless you know what you're doing
2. Find the variable "filePickerTypeEnv" (around line 8)
    * it should look similar to `filePickerTypeEnv = "<Some Value>"`
3. Edit the text in the quotes (<Some Value\> in the example above) and set it to one of the following
    * `gui` or `1` (uses pop-ups for selection, recommended for beginners)
    * `cli` or `2` (uses terminal for selection, recommended for advanced users)
4. Save and exit

### `Permission denied! Unable to create '<directory>'`
This error is caused by the program being unable to create a directory because of lack of permissions from the user

Troubleshooting steps
* Make sure you have permission to edit files in the directory the program is located in

### `Error with <variable> variable`
This error is caused by a variable being unable to initialize after being converted to a specific type. The information about the variable should be in the error message

Troubleshooting steps
* check the .env file and change the incorrect variable or redownload the .env file

### `Program has exited. Please check the 'CV2 loop' variable if this is unintended behavior`
This error is caused by an exception in the CV2 loop variable, exiting the entire script

### `An unknown error occurred`
Unfortunately, we can't account for every error. If this happens, it should say what brought up the error in the console/terminal tab. 
