MyAlfred
========

This is where I am keeping my Alfred 2 extensions. I currently have the following extensions:

**Mjolnir Workflow**

This workflow is for running scripts using Mjolnir to control your windows. This is just a sample of the things that can be done. Follow this layout and you can do many neat things with Mjolnir.

First off, download Mjolnir from https://github.com/mjolnir-io/mjolnir.git. That site also tells how to get started. To get the command line utility, go to https://github.com/asmagill/mjolnir_asm.ipc and follow it's directions.

Once mjolnir and it's cli program is installed, use the "mj:find mjolnir" command to set the path to the executable.

| Command | Description |
|---|---|
|mj:install|This will install some modules that is used in the configuration file for this workflow. It will also install a default configuration file for mjolnir. If you already have one, move it to a temporary location, run this command, and then copy your function to the configuration file. This should be the second command you run to get this workflow running. Since it does download from the web, it will take a while to complete.|
|mj:reload|This tells mjolnir to reload the configuration file.|
|mj:nup|This nudges the current window up.|
|mj:ndown|This nudges the current window down.|
|mj:nleft|This nudges the current window to the left.|
|mj:nright|This nudges the current window to the right.|
|mj:tcaff|This toggles system caffenate.|
|mj:leftthirds|This moves the current window to the left 1/3 of the screen.|
|mj:rightthirds|This moves the current window to the right 2/3 of the screen.|
|mj:snap|This snaps the current window to the closes grid box area.|
|mj:setgrid|This requires you to put the x, y for a starting position in a 3x3 matrix for the current window. Then you give the width and height. Therefore, to move the current window to the upper left most block in a 3x3 matric, you would do "mj:setgrid 0, 0, 1, 1". There is also a hotkey set to this value as an example.|
|mj:command|Type in a command string and it will be sent to Mjolnir directly!|

**Alfred URI Handler**

This workflow has one command "au:install". Once you run it, a URI handler for Alfred will be installed. This is used to trigger external triggers in any workflow. The format is:

alfreduri://com.apple.AppleScript.AlfredURIhandler?wf=&lt;workflow Bundle ID&gt;&amp;arg=&lt;arguments&gt;&amp;ext=&lt;external trigger name&gt;

The arguments should be URI encoded (ie: no spaces, but %20 instead). If you update the workflow, you have to re-apply the handler. Also, do not delete the workflow or the functionality will be removed.

You can also launch a search in Alfred with:

alfreduri://com.apple.AppleScript.AlfredURIhandler?search=&lt;search query&gt;

The search query needs to be URI encoded as well.

**Alfred Time Keeper**
A time tracking extension that allows for any number of projects and tracking the time between them. Still early stage, but very useable. It also has a basic graphical viewing of work hours with a calendar for lookup. I have started recreating some of the PHP scripts as full go language programs. Please let me know if you have any problems. The following keywords are used:
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

**Text Massagers** I am often changing text around to different formats in large quantities. So, I made a workflow for keeping all of them. I call it text massagers because you are "massaging" the text with the script. You can use this as your template for your own massagers. All of these scripts takes the item from the clipboard, massages it, and places back into the clipboard while showing you the results.

| Command | Description |
|---|---|
|&lt;alt&gt;&lt;command&gt;m  | Expects a markdown anchor line in the clipboard and converts it to a HTML anchor within a list item.|
|&lt;alt&gt;&lt;command&gt;t  | Fixes a time into HH:MM:SS format no matter what it was before.|
|&lt;shift&gt;&lt;command&gt;” | Takes the current selection and passes it to the “tm:select” command for selecting the text massager from a list. The list will show the resulting string. It will then perform the selected “massage” to the text and copy it to the clipboard and back into the document it was grabbed from if possible.|
|tm:select|Takes the string on the Alfred Prompt and runs it through the different massagers and shows the output in the list. When the user selects one of the massagers, it will copy the resulting string to the clipboard and to the document that is open.|
|&lt;shift&gt;&lt;alt&gt;&quot;| Takes the current selection and passes it to the “tm:selectn” command for selecting the text massager from a list. It will then perform the selected “massage” to the text and copy it to the clipboard and back into the document it was grabbed from if possible.|
|tm:selectn|Same as "tm:select" except for not displaying the results in the list. This is for slower computers.|

**TextSoap Cleaners** This workflow interfaces with [TextSoap](http://www.unmarked.com/textsoap/), a great text processing program. I now use it more than awk! The following are the keywords defined:

| Command | Description |
|---|---|
| tc:clean | This keyword will present a list of all previously used cleaners to pick from. Start typing to narrow down the list. When you hit enter on an entry, it will perform that cleaner on the clipboard. If you hold down the fn key, it will delete that cleaner from the list of preferred cleaners. You can set a hotkey to repeat the last ran cleaner on the clipboard. |
| tc:full | This keyword will show all available cleaners obtained from the tc:getcleaners. The cleaner you select will be performed on the clipboard and the cleaner will be saved into your list of preferred cleaners. |
| tc:fulla | This keyword is the same as tc:full, but will append the results to the topmost application.  You can set a hotkey to perform this on the current selection as well.|
| tc:seteditor | Allows you to set the text editor for editing the list of preferred cleaners. |
| tc:editlist | Allows you to edit the list of preferred cleaners using the editor already setup. |
| tc:getcleaners | This will query TextSoap for the list of cleaners it has. You should do this each time you create new cleaners you want to use with this workflow. |
| tc:addcleaner | This will set the string given into the list of preferred cleaners. |
| tc:count | This will count the number of lines, words, and characters in the clipboard. If a string is passed with it, it will count that string. You can set a hotkey to count the current selection. |
| tc:loadpopclipext | This will load the popclip extension for executing the last cleaner on the highlighted text. |

There are also three places to set your hotkeys: one for doing a character/word/line count of your selection, one for evoking the last cleaner on selected text, and one for choosing from the full list of cleaner to apply on the currently selected text.

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

**Budget Workflow (formerly Calca Toolkit)** This workflow is for keeping track of budgets <a href="https://itunes.apple.com/us/app/calca/id635758264?mt=12&ign-mpt=uo%3D4">Calca.app</a>. You can set a budget template ("b:budget" keyword and selecting "Edit Template"), and then create budgets each month ("b:budget" keyword and selecting "Make from Template"). The "b:budget" keyword will also show all of the available budget files that you can view and/or edit.

**Notes Workflow (formerly a part of Calca Toolkit)** This workflow if for taking notes. It was designed for Calca, but can be used with any editor. So far, I have the following keywords:

<table>
<tr><td>“n:setnotes" </td> <td>This allows for the setting for the location of your notes directory. It is a directory select. Therefore, the directory has to already exist.</td></tr>

<tr><td>“n:notes" </td> <td>This will list every file in the notes directory that ends in ".txt". You can create a new notes file or open an existing notes file. If you select one of the files while holding the <cmd> key, you can append the contents of the clipboard to the specified notes file. If that is a new file, it will be started with the clipboard contents. You can move the selected file to the trash by holding the <fn> key. This requires the trash command to be in the "/usr/local/bin" directory. You can convert the markdown file to html using the <shift> key when you press <enter> on a file name. This requires the pandoc program to be loaded onto your system. The <alt> key will open the file with Marked.app. </td></tr>

<tr><td>“n:setEditor”</td> <td>This allows you to set the editor that you want to use for editing your notes. It defaults to Calca, but you can set it to any application you want. It will bring up a file selector with applications from your main application folder and your personal applications folder.</td></tr>
</table>

**Todo Workflow**
This workflow is for working with todo lists using TaskPaper or FoldingText. But, you can set any other editor you want as well. Since TaskPaper and FoldingText uses plain text files for everything, it is easy to write scripts to add functionality that the program does not have. So far, I have the following keywords defined:

| Command | Description |
| --------:| ---------- |
| t:settodo | This command allows you to set the directory for your todos. It will setup the supporting files and sub-directories as  well. This is the first action to perform with this workflow. |
| t:createtodaytodo | This command will take the everyday, weekly, monthly, and dated todos and combine them to the left over todos from the last time you created todos. It will also archive the finished todos. Todos that are repeated from the dated category are reset according to the repeat pattern.|
| t:showtoday | This command will open todays (or the most current) todo list in TaskPaper.  |
| t:showyesterday | This command will open yesterdays (or the one before the most current) todo list in TaskPaper.  |
| t:showfinished | This command will open the archived done tasks in TaskPaper.  |
| t:addmonthlytodo | This command will ask for the day of the month and the task. It will then place that in the monthly todo  directory for that day. When a new todo list is created, then it will pull in that days tasks. |
| t:addeveryday | This adds a task to the everyday task list. Every task placed in this list will be added to the current todo list everytime it is created.|
| t:addweekdaytask | This command will ask for the day of the week and the task. It will  then place that it in the weekly todo directory for that day of the week. When a new todo list is created, then it will pull in that days tasks. |
| t:doing | This creates a new dated entry for the current journal. It will ask which journal to place the entry into. The standard  doing.txt journal will automatically be created. |
| t:showdoing | This opens the current doing journal in TaskPaper.  |
| t:showprojects | This opens the projects task file in TaskPaper. This is for ongoing projects and their tasks.  |
| t:sortdone | This command takes the topmost TaskPaper list and sorts all of the done tag entries to the bottom.  |
| t:seteditor | This command is for setting the text editor to use.  |
| t:newjournal | This command will allow you to create new journal files.  |
| t:showjournal | This command is for opening a journal in the editor. It will ask which journal and give you the current list of  journals. |
| t:settz | This command is for setting the time zone. A list of time zones will be given and you select the one you are in.  |
| t:showtz | This command will show the currently set time zone.  |
| t:next | This finds the tag @next, marks that task done, and adds it to the next task. |
| t:adddatedtask | This allows you to add a task on a particular date that can repeat also. You can repeat by days, weeks, months, or years. It also shows all dated tasks and allows for deleting them. |
| t:managemonthly | This allows you to pick a monthly task and edit the file or delete the file. |
| t:manageweekly | This allows you to pick a weekly task to edit or delete. |
| t:editeverydaytask | This allows you to edit the everyday task file. |

**Alfred Bible** This workflow will request Bible passages from the "Ephesians 4:14" website:  http://www.4-14.org.uk/xml-bible-web-service-api.  Access to this API is currently free. This workflow will request the given verse from Alfred edit line or from the current OS X selection, request the verse(s), and return it in the clipboard and a notification. You can then paste it where ever you want. If you use the hotkey to search for the selected verse, it will automatically replace it with the text. There is also a hotkey to paste both versions: English and Thai. It now translates the English Bible book names to Thai. I will be adding more functionality to this workflow in the future and eventually have a full Bible study app. Let me know what functions you need.

**OctoPOW** This workflow assumes you have octopuses and pow installed on your computer with each octopress site linked into the ~/.pow directory. The POW workflow (https://github.com/phallstrom/AlfredPow) is a great compliment to this workflow and is called by the preview function. First, set up your editor with "octopow:editor". Then, set you current POW project with "octopow". You can create/edit/delete posts with "octopow:post". You can generate your site and preview it in POW using "octopow:preview". You can then deploy you changes with "octopow:deploy". This workflow assumes you have already setup your Octopress site and POW programs on your system. More to come!

**Run Chrome with Accessibility** This workflow allows you to launch Chrome with the accessibility flag set so that you can use <a href="http://shortcatapp.com/">ShortCat.app</a> with Chrome. It uses ctl-shift-h to launch Chrome or bring it to the front if running. ctl-shift-alt-h to quit Chrome.

**Sermon Scheduler** This workflow aid in the creating of my sermon schedules. Use ss:setdirectory to set the directory for sermons (or whatever you want to create schedules from a template). The use ss:seteditor to set the editor you want to use (I use Sublime). You then can use ss:create to make a new schedule by the template (you might want to edit the template first with the ss:edit and selecting the template). Then use ss:edit to edit one of the schedules or the template.

The unique thing about the workflow is that new schedule’s name will always be something like: 2014-Feb02-Feb08.md. The current year, first day of the week and the last day of the week. The ss:create gives you names for the current week and the next 4 weeks.

This works great for me being a missionary. You can change it to meet your own needs.

**Scratch Pad** Sometimes you just need a place to edit some text quickly. Or, simply write a short note to store in the clipboard history (it actually works better than you think). That is where this workflow comes in handy.

After you set a hotkey, you can select text and edit it on the Alfred command line. When you press enter, it will be placed into the clipboard. If you press <code><cmd></code> and enter, it will place it into the clipboard and the top most application.

If you invoke the keyword “sp:” or if you press the hotkey without a selection, it will offer to put the clipboard as the text to edit. Press enter on the “clipboard” option and the contents of the clipboard will be copied to the Alfred command line for editing.

**DwellClick Workflow** This workflow has commands for [DwellClick from Pilotmoon](https://pilotmoon.com/dwellclick/). You can:

| Command | Description |
|---|---|
dc:enable   | Enable DwellClick
dc:disable  | Disable DwellClick
dc:action   | Performs the action selected. This is a script filter that will list all possible actions. If the command key is pressed, it delays the action for the next dwell click. If the function key is pressed, then the action is stored for use with the first hotkey action.

The first hotkey action is for performing the stored action. The second is an example of making a fixed action to an hotkey. Very useful.

**Fish Toolbox** This is a toolbox of functions for working with the [Fish Shell](http://fishshell.com/).  You can install fish shell with homebrew:

	brew install fish

Currently, the functions are:

| Command | Description |
|---|---|
f:seteditor  |  Set the code editor to use
f:editfunction |   Edit a Fish function. It will show a list of possible functions to edit. If you press FN key and select a function, that function will be deleted.
f:editconfig  | Edit the Fish Configuration file.
f:newfunction | Create a new fish function.

with more to come.

**Instant Search** This workflow is the translation of Brett Terpstra's LaunchBar script for Alfred. You have to have his Instant Search Service installed. For more information, go to [SearchLink - BrettTerpstra.com](http://brettterpstra.com/projects/searchlink/).

**Powerline Toolbox** This is a toolbox of functions for working with [Powerline](). Currently, the commands are:

| Command | Description |
| --- | --- |
| pl:loc | Gives the location of the pip installation of Powerline. It will open it in Alfred, in Finder if the ctrl key is pressed, or in Terminal if the cmd key is pressed. |
| pl:doc | Will open the documentation for Powerline. |
| pl:fonts | Will open the fonts download page for Powerline. |
| pl:github | Will open the GitHub page for Powerline. |
| pl:editor | Will allow you to set the text editor for editing Powerline configuration files. |
| pl:conf | Will allow you to browse the Powerline configuration directory and edit the files and create new files. |
| pl:goconf | This will open the configuration directory in Alfred or in Finder if the cmd key is pressed. |

**Open in Alfred**

This workflow allows you to open a Terminal window or iTerm windows directory in Alfred.

You type "oa:install" to install a helper script into your /usr/local/bin directory. Make sure that directory exists, is writable by you, and in your path.

   Then you can use these commands:

| Command | Description |
|---|---|
|oa:terminal|open the topmost terminal window in Alfred
|oa:iterm|open the topmost iterm window in Alfred

**Title Case Server**

This workflow goes with an upcoming tutorial on using golang with Alfred on tutplus.com. It currently runs a small web app for doing title case conversions. The workflow has these commands:

| Command | Description |
|---|---|
|tcs:launch|This will start the title case server on port 9910|
|tcs:stop|This will stop the title case server|
|tcs:convert|This will take a string on the Alfred prompt, send it to the title case server, and return the result in a notification and the clipboard.|

It also has a hotkey specified to take the selected text, convert it, and paste it back in place. You will have to set the hotkey yourself. The go source code is included in the workflow.

**Folding Text Workflow**

This workflow is a work in progress. As I come up with more things I want to do with Folding Text program, I will be adding to this workflow. If there is something you would like to see added, just let me know. Most of the functions I found on the FoldingText website and compiled them here for easy use. The new bookmarking feature is the coolest thing!

| Command | Description |
|---|---|
| ft:autofocus | This does the autofocus workflow. Move the todo at the current cursor to the bottom most "# Autofocus.todo" list. It creates one if there is not one. |
| ft:next | Find the "@next" todo tag, makes it @done, and sets the next todo as @next. |
| ft:marked | Open the current file in Marked.app |
| ft:tagremove | Gives a list of tags in the current document and will remove all the ones selected in the list. |
| ft:safari | This gets the tabs in the current Safari Web Browser and copies their addresses to the topmost FoldingText document. |
| ft:chrome | This gets the tabs in the current Chrome Web Browser and copies their addresses to the topmost FoldingText document. |
| ft:countunfolded | This will count all the characters, words, and lines of text that is not folded. Great for geting word counts of an article with all non-essential areas folded away! |
| ft:getvisible | This copies all the unfolded text to the clipboard. |
| ft:open | This will allow you to open any FoldingText, Markdown, or plain txt files in your home directory. It looks for the ‘ft’, ‘md’, ‘txt’ extensions. |
| ft:gototag | This will list every tag in the topmost document. When you select one, all lines without that tag are folded away. Place the cursor in a line and unfold and you are there in the document. |
| ft:openfilelist | This will open every file you have in the FoldingText file list. |
| ft:AddFile | This file action allows you to place files in to your FoldingText file list. |
| ft:showfiles | This shows you every file in your file list. Selecting one will open just that one file, or bring it to the front if it is already open. Select a file with cmd and the file will be taken off the list (but not touched on the HD). |
| ft:docs | This gives a list of FoldingText documentation documents you can select and open.|
| ft:addurihandler | This adds a system script to handle "ftdoc://" URIs by loading the file specified in FoldingText. It works to launch bookmarks to files and a location in the file. |
| ft:mbkmark | This gets a URI for the current cursor location in the topmost FoldingText document and adds it to the bookmark list. You have to supply a name for the bookmark. |
| ft:bookmarks | This shows every bookmark and allows you to open it, remove it (function key), or create a markdown link to the bookmark and paste into the topmost application (command key). |
| ft:inbox | This allows you to add a message line to the end of a block with the @inbox tag. |
| ft:notetag | This one will get a list of tags in the top FoldingText document. The user can select a tag and then give a message. That message will be added to the end of that tag node. |
| Site Layout | This is a File Action that you can trigger in the Alfred browser on directories only. When you run it, it creates a file of the directory structure there down with clickable links to each file for FoldingText. You have to have the FoldingText URI handler installed. Once created, it will open the file in FoldingText. The lastest version makes use of [Alfred URI Handler](https://github.com/raguay/MyAlfred/blob/master/AlfredURIHandler.alfredworkflow).|
| ft:lastsitelayout | This will show the last layout generated by the **Site Layout** directory action.|

**Time Adding Workflow**

 I am often needing to add up a series to times in a document. This workflow makes it very easy. Clear the accumulator, select a time value, and hit your hotkey combination you assigned in this workflow. The time will be accumulated. You can show the time in Hr:min:sec format or just plain minutes. Have fun!

| Command | Description |
|---|---|
| ta:clear   | This clears the accumulator |
| ta:showmin | Show the accumulated time in just minutes. |
| ta:showhr  | Show the accumulated time |

There is a hotkey you need to set for adding the currently selected time.

**Zip Info**
This workflow has one command:  zi:view. This will show you the zip files in your home directory's Documents folder. When you select one, it will open a Python window showing the contents of the zip file.

****

Please let me know if you have any problems, suggestions, or commits. These are documented more fully on my web site <a href="http://customct.com">http://customct.com</a>.

**goAlfred** I created a library in the <a href="http://www.golang.org">go language from Google</a> to make it easier to create your Alfred workflow. You can see the library here: <a href="https://github.com/raguay/goAlfred">goAlfred</a>
