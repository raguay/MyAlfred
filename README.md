MyAlfred
========

This is where I am keeping my Alfred 2 extensions. I currently have the following extensions:

**Alfred Time Keeper** A time tracking extension that allows for any number of projects and tracking the time between them. Still early stage, but very useable. It also has a basic graphical viewing of work hours with a calendar for lookup.

**Name Sequencer** This workflow allows you to sequence through some file names. You set the base name and extension. It will increment the count and place it in the clipboard and Growl it. If there is a file name in the clipboard, you can also just increment the count for the file name.

**Video Time** This workflow is used to find the duration of a video. 

**Compress PNG Image** This workflow is for compressing png images to a smaller size with scaling. You have to edit the script to your image size you want to scale. Type "ci" and then a name of the image file. A list of images will be shown for you to select the one you want to compress. When using Alfred to browse files, if you view a directory, the  compress image command will show in the right arrow menu listing. You can then compress all the files in that directory. You have to have the Image Magick library and utilities already installed to use this workflow.

**Next Item**  This little workflow allows you to sequentially step through items in a file. You use the "Next Item: Set File" file action on the file containing a list of items: One item per line. For example, a list of urls; one per line. Then the hot key (you will have to set yourself since mine will be erased) will take the next item from the list and copy it to the clipboard. "ni:inc" and "ni:dec" will increment or decrement the counter. "ni:set" allows you to set the counter to any number. "ni:clear" will clear the counter. Setting a new list will clear the count. The file specified is copied to a work area that all the other scripts will use to access it. Therefore, you do not need to worry about the original file being changed.

