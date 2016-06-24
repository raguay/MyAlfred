# MyAlfred 3

This is where I am keeping my Alfred 3 workflows. Every workflow in this directory is guarenteed to work with Alfred 3. As I verify my Alfred 2 conversions to Alfred 3, they will be placed here. 

To install a wokflow, it is best to download the whole repository as a zip and then double-click on the workflow you want to install into your Alfred. I currently have the following workflows:

## Quiver Workflow

This workflow allows you to create templates with Handlebar syntax inside of the [Quiver](http://happenapps.com/#quiver) program. To use the workflow, you have to have Node.js installed first. I recommend using [Homebrew](http://brew.io) to install it.

Once Node.js is installed, go to your Quiver Library file in Alfred Browser and select the “Set Quiver Library” file action. This tells the workflow where your templates (or snippets) are to be kept. Create a workbook called “Snippets” with one note called Defaults. The Defaults note has to have one code block set to JSON and the defaults for the Handlebar expansions set. The rest of the notes will be templates. Once you create or load the Snippets Notes, run the **qw:runint** command to set it up.

When you run “qt”, it will list all of your template files in the Snippets notebook. When you select one, it will be expanded with any json cells in the note and the Defaults json data. The help files explain more than this does.

There are the special helper function for Handlebars that are defined. They are:

{{env &lt;environment variable&gt;}}

This command will be replaced in the snippet with the specified environment variable.

{{clip &lt;num&gt;}}

This command will be replaced in the snippet with the specified clipboard history. the _num_ is zero referenced (ie: begins with zero being the current clipboard contents). The largest value for _num_ depends on the environment variable setting for _clipHist_. The default value is 5. The clipboard history is taken from **Alfred**'s database of clipboard history.

{{save &lt;name&gt; &lt;text&gt;}}

This command creates a helper named “&lt;name&gt;” with the expanding text of “&lt;text&gt;”. It also places the given “&lt;text&gt;” at the point of definition. This allows you to create text snippets on the fly inside the template. Very handy.

{{clpboard}}

This helper command places the current clipboard contents at the point in the template. This command is using the command line command _pbpaste_ to get the clipboard contents.

{{date &lt;format&gt;}}

This will format the current date and time as per the format string given. See the help document that is loaded upon initialization.

{{date &lt;date/time&gt; &lt;format&gt;}}

This takes the date/time string and formats it according to the format given.  See the help document that is loaded upon initialization.


The following data expansions are defined as well:

{{cDateMDY}} gives the current date in Month Day, 4-digit year format

{{cDateDMY}} gives the current date in Day Month 4-digit Year format

{{cDateDOWDMY}} gives the current date in Day of Week, Day Month 4-digit year format

{{cDateDOWMDY}} gives the current date in Day of Week Month Day, 4-digit year format

{{cDay}} gives the current date in Day format

{{cMonth}} gives the current date in Month format

{{cYear}} gives the current date in 4-digit year format

{{cMonthShort}} gives the current date in Short Month name format

{{cYearShort}} gives the current date in 2-digit year format

{{cDOW}} gives the current date in Day of Week format

{{cMDthYShort}} gives the current date in Month day 2-digit year format

{{cMDthY}} gives the current date in Month Day 4-digit year format

{{cHMSampm}} gives the current date in h:mm:ss a format

{{cHMampm}} gives the current date in h:mm a format

{{cHMS24}} gives the current date in H:mm:ss 24 hour format

{{cHM24}} gives the current date in H:mm 24 hour format

There is more to come!

## TextSoap Cleaners

This workflow interfaces with [TextSoap](http://www.unmarked.com/textsoap/), a great text processing program. I now use it more than awk! The following are the keywords defined:

| Command           | Description |
| ----------------- | ----------- |
| tc:clean          | This keyword will present a list of all previously used cleaners to pick from. Start typing to narrow down the list. When you hit enter on an entry, it will perform that cleaner on the clipboard. If you hold down the fn key, it will delete that cleaner from the list of preferred cleaners. You can set a hotkey to repeat the last ran cleaner on the clipboard. |
| tc:full           | This keyword will show all available cleaners obtained from the tc:getcleaners. The cleaner you select will be performed on the clipboard and the cleaner will be saved into your list of preferred cleaners. |
| tc:fulla          | This keyword is the same as tc:full, but will append the results to the topmost application.  You can set a hotkey to perform this on the current selection as well. |
| tc:seteditor      | Allows you to set the text editor for editing the list of preferred cleaners. |
| tc:editlist       | Allows you to edit the list of preferred cleaners using the editor already setup. |
| tc:getcleaners    | This will query TextSoap for the list of cleaners it has. You should do this each time you create new cleaners you want to use with this workflow. |
| tc:addcleaner     | This will set the string given into the list of preferred cleaners. |
| tc:count          | This will count the number of lines, words, and characters in the clipboard. If a string is passed with it, it will count that string. You can set a hotkey to count the current selection.|
| tc:loadpopclipext | This will load the popclip extension for executing the last cleaner on the highlighted text.|

There are also three places to set your hotkeys: one for doing a character/word/line count of your selection, one for evoking the last cleaner on selected text, and one for choosing from the full list of cleaner to apply on the currently selected text.