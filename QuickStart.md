# Quick Start Guide #

This brief guide should have LinkedIn connectivity up and running in a few short minutes.



<p align='right'></p>


---


## Sign-up for a LinkedIn Application Key ##

Before starting, you'll need an application token (a key pair) from LinkedIn. You can apply for a key [here](https://www.linkedin.com/secure/developer); be sure to keep this key pair handy - you'll need in in a few moments.

<p align='right'><a href='QuickStart#Quick_Start_Guide.md'>^ Top</a></p>

## Downloading the Required Files ##

  * Download the latest version of the script, demo scripts and support image from the '[Downloads](http://code.google.com/p/simple-linkedinphp/downloads/list)' page;
  * Download the stand-alone [OAuth library from Google Code](http://oauth.googlecode.com/svn/code/php/).

<p align='right'><a href='QuickStart#Quick_Start_Guide.md'>^ Top</a></p>

## Installing the Files ##

Once you have the needed files, unzip them and place them on your web server in a location that can be accessed by your user-facing PHP scripts.

By default, the Simple-LinkedIn class file will look for the OAuth class in the same directory - should you need to change this, simply change the following line, found near the top of the Simple-LinkedIn class file as needed:

```
require_once('OAuth.php');
```

### Verifying the Install ###

As the library includes a set of demonstration scripts, once you have dropped the files on your server you can then use them to verify that communications are working.

  1. From the Simple-LinkedIn .zip file, unzip the demonstration files to a location on your web server that is accessible via a browser;
  1. Modify each of the demonstration files, first changing the `require_once()` line, pointing them at the recently installed Simple-LinkedIn class:
```
require_once('linkedin_X.X.X.class.php');
```
  1. Now, insert your LinkedIn application key pair into the $API\_CONFIG configuration array:
```
$API_CONFIG = array(
  'appKey'       => '<your application key here>',
  'appSecret'    => '<your application secret here>',
  'callbackUrl'  => NULL 
);
```
  1. Finally, point your browser at the demo scripts and authorize yourself against LinkedIn with your new application. Once authorized, the demo scripts will become functional, and the install will have been validated.

<p align='right'><a href='QuickStart#Quick_Start_Guide.md'>^ Top</a></p>

## Including Simple-LinkedIn in your Project ##

Now that you've signed up for application keys, and downloaded, installed and verified the library, you can now start building your LinkedIn API application.

Following the example of the demo scripts, include the Simple-LinkedIn class file in your PHP file/class. You can use relative or absolute paths, as with any PHP include/require:

```
require_once('/path/to/linkedin_X.X.X.class.php');
```

Then, instantiate the LinkedIn object by using the same configuration array from the demo scripts that contains your LinkedIn API key pair:

```
$API_CONFIG = array(
  'appKey'       => '<your application key here>',
  'appSecret'    => '<your application secret here>',
  'callbackUrl'  => NULL 
);
$linkedin = new LinkedIn($API_CONFIG);
```

The final step is to authorize the viewer - the demo scripts contain an example of how to achieve this, but in essence you want to store the user's access token locally so that you can make repeated calls on their behalf to the LinkedIn platform.

<p align='right'><a href='QuickStart#Quick_Start_Guide.md'>^ Top</a></p>

## Latest Changes, Notes ##

With the basics up and running, be sure to check the [Release Notes](ReleaseNotes.md) for the latest information on the current version of the Simple-LinkedIn class. Additionally, the [Change Log](ChangeLog.md) details all changes from version to version.


<p align='right'><a href='QuickStart#Quick_Start_Guide.md'>^ Top</a></p>

## Spread the Word ##

Now that you are using the class, indicate it on [Ohloh](https://www.ohloh.net) and help spread the word about this free open-source library by clicking the 'I Use It' button below!

&lt;wiki:gadget url="http://www.ohloh.net/p/588064/widgets/project\_users\_logo.xml" height="43" border="0"/&gt;

<p align='right'><a href='QuickStart#Quick_Start_Guide.md'>^ Top</a></p>