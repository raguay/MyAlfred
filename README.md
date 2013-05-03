MyAlfred
========

This is where I am keeping my Alfred 2 extensions. I currently have the following extensions:

**Alfred Time Keeper** A time tracking extension that allows for any number of projects and tracking the time between them. Still early stage, but very useable. It also has a basic graphical viewing of work hours with a calendar for lookup.

**Name Sequencer** This workflow allows you to sequence through some file names. You set the base name and extension. It will increment the count and place it in the clipboard and Growl it. If there is a file name in the clipboard, you can also just increment the count for the file name.

**Video Time** This workflow is used to find the duration of a video. You can use the 'getvideotime' keyword to search for a particular video to get the duration. The 'getvideodir' keyword is used to scan a full directory. Both are also file actions in the Alfred browser.

**Compress Image** This workflow is for compressing png images to a smaller size with scaling. You have to edit the script to your image size you want to scale. Type "ci" and then a name of the image file. A list of images will be shown for you to select the one you want to compress. When using Alfred to browse files, if you view a directory, the  compress image command will show in the right arrow menu listing. You can then compress all the files in that directory. You have to have the Image Magick library and utilities already installed to use this workflow. You can now use the 'ci.ext' command to set the extension of the final image, which will cause conversion if set to a different type. I also added the 'png-jpg' and 'jpg-png' commands to simply convert the specifed images to the other format. The ImageMagick library is included now due to many people having problems installing it.

**Next Item**  This little workflow allows you to sequentially step through items in a file. You use the "Next Item: Set File" file action on the file containing a list of items: One item per line. For example, a list of urls; one per line. Then the hot key (you will have to set yourself since mine will be erased) will take the next item from the list and copy it to the clipboard. "ni:inc" and "ni:dec" will increment or decrement the counter. "ni:set" allows you to set the counter to any number. "ni:clear" will clear the counter. Setting a new list will clear the count. The file specified is copied to a work area that all the other scripts will use to access it. Therefore, you do not need to worry about the original file being changed.

**Text Massagers** This is an example workflow of ways to process text in the clipboard and stuff it back. I use all of these almost everyday. The first one is changing a Markdown anchor tag to HTML. The second removes "streaming=off" from a WordPress shortcode and replaces it with "streaming=on". Also, there is a text massager for fixing time stamps. It will make sure the time stamp in the clipboard is "00:00:00" format. It adds "0" padding as needed. This one is not AlleyOOP enabled since it is intended as a demonstration of doing text manipulation with Alfred. 

All workflows now work with AlleyOop, except where mentioned otherwise. Please let me know if you have any problems, suggestions, or commits. These are documented more fully on my web site <a href="http://customct.com">http://customct.com</a>.