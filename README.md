# Jibo: Simple Timer behavior for developers

## Skill Description

This skill adds a simple visual timer built with CSS to Jibo. It is intended to be used by Jibo SDK developers to have an easy way to incorporate a visual timer into their own

skills quickly and with no coding.

https://cloud.githubusercontent.com/assets/3519552/14385649/f17aedf8-fd77-11e5-882b-6eed719a0e16.jpg

**Image: simpleTimer using 60 sec. countdown with default options**

## Dependencies

This skill requires the jQuery Node package to run correctly.

## Installation

1. You only need 2 files added to your skill to incorporate simpleTimer.  Copy "behaviors/simpleTimer.bt" to your behaviors folder and "styles/simpleTimer.css" to your styles

folder.
1. Add the following 2 lines inside the <head> of your index.html file:
    <link rel="stylesheet" type="text/css" href="styles/simpleTimer.css" />
    <link href='https://fonts.googleapis.com/css?family=Roboto:300,100' rel='stylesheet' type='text/css'>
3. Add the jQuery Node package to your skill via the command line. Just navigate to your skill's folder and use npm install jQuery.

## Usage

To use simpleTimer inside of your own skill, just add a Subtree behavior wherever you want the timer to appear and point the behaviorPath argument to simpleTimer.bt.

By default, the timer runs for 60 seconds with a dynamic blue status band surrounding a simple counter displaying an abbreviation of the amount of time left and a full counter

just below it displaying additional countdown information.

To set the timer duration, send it via the getNotepad argument using timerDurationMS (in milliseconds):

() => {
	return {

		timerDurationMS:30 * 1000 // 30 seconds
	};

}

The timerDurationMS option can accept durations as high as a number of days (e.g. for a 5-day timer, use 5 * 24 * 60 * 60 * 1000) although recommended usage is for short

durations.

The simpleTimer behavior also has additional options which you can use to customize the display of your timer:

() => {
	return {

		timerDurationMS:3 * 60 * 1000 // set the timer duration (default:60 seconds)
		timerStatusColor:"#f7b84e", // set the active color of the status band (default:#0099ff,blue)
		timerShowStatus:true, // toggle the display of the status band. (default:true) NOTE: When hidden, the timer shows on top of the eye.
		timerShowSimpleCounter:false, // toggle the display of the simple counter (default:true)
		timerShowFullCounter:true // toggle the display of the full counter (default:true)
	};

}

EXAMPLE #1 - With the timerShowFullCounter set to false and the status color set to yellow (#f7b84e):
[image]

EXAMPLE #2 - With the timerShowStatus set to false:
[image]

## FAQs

What's with the call to fonts.googleapis.com in your installation instructions?
For a clean, crisp timer display, I decided to use the Roboto font in the timer styles. If you don't want to use it for any reason, feel free to leave that line out of your

<head> tag and use the default font instead.

Can I make modifications to simpleTimer?
Absolutely! You may choose to modify the behavior itself or just the CSS in any way you wish to match the needs of your skill.  If you would like to share your changes with

others, please fork them via GitHub: https://github.com/michaelrod77/jibo-simpleTimer.git
