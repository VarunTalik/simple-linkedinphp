**NOTE** - there is a major bug with v3.3.0 of the library - a fix is in the works, but will not be posted until 01/31/2012. Please use v3.2.0 of the code until then. Thanks for your patience.

For the latest project updates, be sure to follow us on Twitter [@SimpleLinkedIn](http://twitter.com/SimpleLinkedIn).

**Also, if you are using the library on a live site/project, get in touch with me for some free press - I'll be promoting companies/sites that are using the library in the near future.**

# Introduction #

This PHP class is designed to be a simple, stand-alone wrapper for the most-used functionality of the [LinkedIn API platform](https://developer.linkedin.com/). Along with the stand-alone [OAuth PHP library](http://oauth.googlecode.com/svn/code/php/), you should have LinkedIn API connectivity up in just minutes. The PHP cURL library is the only pre-requisite for this library; an exception will be thrown if it is not found.

Simple-LinkedIn has been designed for, and tested on, PHP5.2+. Due to the [object model changes](http://www.php.net/manual/en/migration5.oop.php) made from PHP4 -> PHP5 it has not been tested and is not expected to work on PHP4. If someone wants to take the code and back-port it to PHP4, feel free to do so and let me know!

## Advantages of this Library ##

By using a stand-alone OAuth/LinkedIn API solution like this, you don't need to install any server/PHP extensions, which usually require some form of root access (not available on many hosts). Simply upload the files, pop-in your API keys and away you go.

## Latest Release ##

The latest stable version of the library can be found in the left-hand column under 'Featured', or under the '[Downloads](http://code.google.com/p/simple-linkedinphp/downloads/list)' tab above.

### Release Notes ###

For a full run-down of the latest version, be sure to read the [Release Notes](ReleaseNotes.md).

### Quick Start ###

Get up and running quickly using the [Quick Start Guide](QuickStart.md).

### Live Demo ###

A working live demo of the library can be found here:

  * http://www.simplelinkedin.com

Note that the demo pages are subject to the same LinkedIn-enforced throttling limits that your applications are, so if traffic is heavy on a given day you may get throttling notices.

### Change Log ###

A full list of changes by version can be found on the project [Change Log](ChangeLog.md).

### Known Issues ###

All current known bugs/issues are located under the '[Issues](http://code.google.com/p/simple-linkedinphp/issues/list)' tab. **If you find a bug or deficiency, please [open a bug report!](http://code.google.com/p/simple-linkedinphp/issues/list)**

If your environment already has the PECL OAuth extension installed, this library is **not for you**. The OAuth library used by the Simple-LinkedIn class is not compatible with the PECL library. Simple-LinkedIn will raise an exception if the PECL OAuth library is enabled on the server.

## Development Release ##

The latest development release can be found under the '[Source](http://code.google.com/p/simple-linkedinphp/source/checkout)' tab and accessed via Subversion (SVN). Note: the development release is just that; development code that is not suitable for a production environment.

## Spread the Word ##

If you are using the class, indicate it on [Ohloh](https://www.ohloh.net) and help spread the word about this free open-source library by clicking the 'I Use It' button below!

&lt;wiki:gadget url="http://www.ohloh.net/p/588064/widgets/project\_users\_logo.xml" height="43" border="0"/&gt;