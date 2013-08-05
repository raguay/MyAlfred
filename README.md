MyAlfred
========

This is where I am keeping my Alfred 2 extensions. I currently have the following extensions:

**Alfred Time Keeper** A time tracking extension that allows for any number of projects and tracking the time between them. Still early stage, but very useable. It also has a basic graphical viewing of work hours with a calendar for lookup. I have started recreating some of the PHP scripts as full go language programs. Please let me know if you have any problems. The following keywords are used:
<table>
<tr><td>atk:addproject</td><td>This allows you to create a new project</td></tr>
<tr><td>atk:project</td><td>This allows you to set the current project</td></tr>
<tr><td>atk:state</td><td>This allows you to set the current state of a project.</td></tr>
<tr><td>atk:help</td><td>Gives a list of commands for Alfred Time Keeper</td></tr>
<tr><td>atk:current</td><td>This will show the current project, time, and state.</td></tr>
<tr><td>atk:week</td><td>This shows the time for the current project this week.</td></tr>
<tr><td>atk:month</td><td>This shows the time for the current project this month.</td></tr>
<tr><td>atk:worktime</td><td>This displays the time worked on all project for a particular day.</td></tr>
</table>

**Name Sequencer** This workflow allows you to sequence through some file names. You set the base name and extension. It will increment the count and place it in the clipboard and Growl it. If there is a file name in the clipboard, you can also just increment the count for the file name.
<table>
<tr><td>setname</td><td>This will set the base name for creating filenames.</td></tr>
<tr><td>setext</td><td>This will set the extension for the filenames created.</td></tr>
<tr><td>clearcount</td><td>This will set the counter back to zero.</td></tr>
<tr><td>inccount</td><td>This will increment the counter by one.</td></tr>
<tr><td>deccount</td><td>This will decrement the counter by one.</td></tr>
</table>

**Video Time** This workflow is used to find the duration of a video. You can use the 'getvideotime' keyword to search for a particular video to get the duration. The 'getvideodir' keyword is used to scan a full directory. Both are also file actions in the Alfred browser.

**Compress Image** This workflow is for compressing png images to a smaller size with scaling. You have to edit the script to your image size you want to scale. Type "ci" and then a name of the image file. A list of images will be shown for you to select the one you want to compress. When using Alfred to browse files, if you view a directory, the  compress image command will show in the right arrow menu listing. You can then compress all the files in that directory. You have to have the Image Magick library and utilities already installed to use this workflow. You can now use the 'ci.ext' command to set the extension of the final image, which will cause conversion if set to a different type. I also added the 'png-jpg' and 'jpg-png' commands to simply convert the specifed images to the other format. The ImageMagick library is included now due to many people having problems installing it.

**Next Item**  This little workflow allows you to sequentially step through items in multiple list files. You use the "Next Item: Set File" file action on the file containing a list of items: One item per line. For example, a list of urls; one per line. Then the hot key (you will have to set yourself since mine being <alt><command>n will be erased) will take the next item from the specified first list and copy it to the clipboard and to a notification. If you view all lists before the first list, you will see each corresponding item for each list. The counter is only incremented after passing the item from the first list.
<table>
<tr><td>"ni:move #"</td><td>This will move the last set file to the # list. If you do not move the file items to a list number, then it will not get sent to you.</td></tr>

<tr><td>"ni:item"</td><td>This will give the next item from the first list and increment the counter.</td></tr>

<tr><td>ni:l #"</td><td>This will give the next item from the # list, but the count will not be incremented unless it is list 1.</td></tr>

<tr><td>"ni:inc" and "ni:dec"</td><td>These will increment or decrement the counter. </td></tr>

<tr><td>"ni:set"</td><td>allows you to set the counter to any number. </td></tr>

<tr><td>"ni:clear"</td><td>will clear the counter and erase the temporary files. </td></tr>

<tr><td>"ni:current"</td><td>will display the current count number.</td></tr>
</table>
The items are addressed using a zero reference. Therefore, if the counter is 1, the the second line in the file will be displayed.

Setting a new list will clear the count. The file specified is copied to a work area that all the other scripts will use to access it. Therefore, you do not need to worry about the original file being changed.

**Text Massagers** This is an example workflow of ways to process text in the clipboard and stuff it back. I use all of these almost everyday. The first one is changing a Markdown anchor tag to HTML. The second removes "streaming=off" from a WordPress shortcode and replaces it with "streaming=on". Also, there is a text massager for fixing time stamps. It will make sure the time stamp in the clipboard is "00:00:00" format. It adds "0" padding as needed. This one is not AlleyOOP enabled since it is intended as a demonstration of doing text manipulation with Alfred.

**TextSoap Cleaners** This workflow allows the running of the various TextSoap cleaners on the current clipboard contents. It remembers past cleaners and gives them as an option. Or, you can popup the full list of cleaners to use. If you start typing the name of a already picked cleaner, it will narrow down the list to cleaners that match what you type. Just added a hotkey setup to perform the last cleaner on the currently selected text and place it back.

**ExpanDrive Toolkit** This workflow gives some added features for ExpanDrive. You can use the hotkey "<ctrl><alt><cmd>e" to change the current selection in Finder or Path Finder that is in a subdirectory for a ExpanDrive drive to a web facing reference to that file. You set up the ExpanDrive name using the "ed:edir" keyword. You then can set the web facing directory prefix with "ed:wdir". The scripts currently do not check for accuracy, that is up to the user.

**s3cmdToolkit** This workflow gives the ability to upload files to Amazon S3 using the s3cmd commandline function. You can download the s3cmd utility at <a href="http://s3tools.org/s3cmd">http://s3tools.org/s3cmd</a>. The workflow currently contains a copy of the s3cmd tool. You will need to open a terminal to the directory that contains the workflow to set your s3 credentials. Please see the directions at <a href="http://s3tools.org/s3cmd">http://s3tools.org/s3cmd</a> to know how to set it up. Here are the currently supported keywords and file actions:
<table>
<tr><td>"s3c:copydir"</td><td>This keywork allows you to pick a directory that contains videos (mp4|mov). The videos will be copied to the corresponding directory on s3. Make sure to set the base directory using "s3c:base".</td></tr>
<tr><td>"s3c:base"</td><td>You use this keyword to set the base directory for s3. It should be the format of "s3://{bucket}/directory/..". It has to be set to "s3://{bucket name}" as the minimum.</td></tr>
<tr><td>"s3c:target"</td><td>This keyword is used to set a target directory under the base directory to copy individual files to s3 using the file action.</td></tr>
<tr><td>"s3c:webheader"</td><td>This keyword is used to set a web header for getting a web friendly url to an item in your s3.</td></tr>
<tr><td>"s3c:sbase"</td><td>This will show the base directory in a notification.</td></tr>
<tr><td>"s3c:starget"</td><td>This will show the target directory in a notification.</td></tr>
<tr><td>"s3c:swebheader"</td><td>This will show the header to make a web friendly address in a notification.</td></tr>
<tr><td>"s3c:copy file"</td><td>This file action will copy the file in the Alfred browser to the base and target directory on s3.</td></tr>
<tr><td>"s3c:list"</td><td>This keyword action allows you to browse your S3 directory. If you hit "cmd-enter" on an item, it will download it to your Download directory. If you hit "alt-enter" on an item, it will set that directory as your target directory for uploading files. If you hit "ctl-enter" on an item, it will push a web facing friendly url for that item in to the clipboard. If you hit "shift-enter" on an item, it will set the items directory as the base directory for future browsing. If you hit "function-enter" on an item, you can move the item to a new name or location. It will prompt for the new location with a copy of the original item twice. You change the second one. If you start typing after the keyword, your selection will be reduced to selections that match what you type.</td></tr>
<tr><td>"s3c:configure"</td><td>This keyword will open a terminal and start the configuration process for the s3cmd command line tool. This has to be done before using the other commands.</td></tr>
</table>

**Calca Toolkit** This workflow is for keeping track of budgets and notes using the <a href="https://itunes.apple.com/us/app/calca/id635758264?mt=12&ign-mpt=uo%3D4">Calca.app</a>. You can set a budget template ("calca:budget" keyword and selecting "Edit Template"), and then create budgets each month ("calca:budget" keyword and selecting "Make from Template"). The "calca:budget" keyword will also show all of the available budget files that you can edit. You can use the "calca:notes" keyword to see available notes to edit or create a new one from scratch giving the title in the Alfred command line. If you hold down the command key while pressing enter, it will paste the contents in the clipboard to the selected file.

**Alfred Bible** This workflow will request Bible passages from the "Ephesians 4:14" website:  http://www.4-14.org.uk/xml-bible-web-service-api.  Access to this API is currently free. This workflow will request the given verse from Alfred edit line or from the current OS X selection, request the verse(s), and return it in the clipboard and a notification. You can then paste it where ever you want. If you use the hotkey to search for the selected verse, it will automatically replace it with the text. I will be adding more functionality to this workflow in the future and eventually have a full Bible study app.

All workflows now work with AlleyOop, except where mentioned otherwise. Please let me know if you have any problems, suggestions, or commits. These are documented more fully on my web site <a href="http://customct.com">http://customct.com</a>.

**goAlfred** I created a library in the <a href="http://www.golang.org">go language from Google</a> to make it easier to create your Alfred workflow. You can see the library here: <a href="https://github.com/raguay/goAlfred">goAlfred</a>
