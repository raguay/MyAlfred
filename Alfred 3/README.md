# MyAlfred 3

This is where I am keeping my Alfred 3 workflows. Every workflow in this directory is guarenteed to work with Alfred 3. As I verify my Alfred 2 conversions to Alfred 3, they will be placed here. 

To install a wokflow, it is best to download the whole repository as a zip and then double-click on the workflow you want to install into your Alfred. I currently have the following workflows:

## Quiver Workflow

This workflow allows you to create templates with Handlebar syntax inside of the [Quiver](http://happenapps.com/#quiver) program. To use the workflow, you have to have Node.js installed first. I recommend using [Homebrew](http://brew.io) to install it.

Once Node.js is installed, go to your Quiver Library file in Alfred Browser and select the “Set Quiver Library” file action. This tells the workflow where your templates (or snippets) are to be kept. Create a workbook called “Snippets” with one note called Defaults. The Defaults note has to have one code block set to JSON and the defaults for the Handlebar expansions set. The rest of the notes will be templates. Once you create or load the Snippets Notes, run the **qw:runint** command to set it up.

When you run “qt”, it will list all of your template files in the Snippets notebook. When you select one, it will be expanded with any json cells in the note and the Defaults json data. The help files explain more than this does.

There are four special helper function for Handlebars defined. They are:

{{env <environment variable>}}
This command will be replaced in the snippet with the specified environment variable.

{{clip <num>}}
This command will be replaced in the snippet with the specified clipboard history. the _num_ is zero referenced (ie: begins with zero being the current clipboard contents). The largest value for _num_ depends on the environment variable setting for _clipHist_. The default value is 5. The clipboard history is taken from **Alfred**'s database of clipboard history.

{{save <name> <text>}}
This command creates a helper named “<name>” with the expanding text of “<text>”. It also places the given “<text>” at the point of definition. This allows you to create text snippets on the fly inside the template. Very handy.

{{clpboard}}
This helper command places the current clipboard contents at the point in the template. This command is using the command line command _pbpaste_ to get the clipboard contents.

{{date <format>}}
This will format the current date and time as per the format string given. See the help document that is loaded upon initialization.

{{date <date/time> <format>}}
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

