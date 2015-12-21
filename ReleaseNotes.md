# Release Notes #

Detailed information on the latest version of the Simple-LinkedIn library. See the [Quick Start Guide](QuickStart.md) for information on using the library.



<p align='right'></p>


---


## Version 3 ##

### Version 3.3.0 ###

New features: Added support for two Groups API related bits of functionality that we missed in the last release:
  * `createPostComment()`, `deletePostComment()`.

We've also added a new `exchangeToken()` method, allowing the user to automate (as much as possible) the [token exchange process](https://developer.linkedin.com/documents/exchange-jsapi-tokens-rest-api-oauth-tokens).

To support/demo this added functionality, we've added a pair of new pages to the demo scripts, tokenExchange.html, tokenExchange.php. These pages need to be located on a secure host (HTTPS) to function - once you have them there, load up the tokenExchange.html page and use it to authenticate against the LinkedIn via the JavaScript API. Once you have done that, your OAuth 2.0 bearer token will be passed to tokenExchange.php, which will then perform the exchange using the new library functionality.

A live demo of these scripts can be found here:

https://simplelinkedin.fiftymission.net/demo/exchange/tokenExchange.html

There are some additional changes to a few method signatures, and a few 'clean-up' items.

Full details can be found in the [Change Log](ChangeLog#Version_3.3.0.md)

<p align='right'><a href='ReleaseNotes#Release_Notes.md'>^ Top</a></p>


---


### Version 3.2.0 ###

New features: Added support for the Groups API related functionality, including the new methods:
  * `createPost()`, `deletePost()`, `flagPost()`, `followPost()`, `group()`, `groupMemberships()`, `groupPost()`, `groupPostComments()`, `groupPosts()`, `groupSettings()`, `joinGroup()`, `leaveGroup()`, `likePost()`, `removeSuggestedGroup()`, `setGroupSettings()` and `suggestedGroups()`.

We've also added a new `raw()` method, allowing the user to make calls directly to the API end-points, allowing for support for API functionality that has not been included in the class. Note that when making the `raw()` call, you must manually check the response code to judge success, as different endpoints respond with different HTTP codes. For example:

```
$response = $OBJ_linkedin->raw('GET', '/people/~');
if($response['info']['http_code'] === 200) {
  // success
} else {
  // failure
}
```

We've also added an accompanying groups demo script to show-off some of the functionality.

Full details can be found in the [Change Log](ChangeLog#Version_3.2.0.md)

<p align='right'><a href='ReleaseNotes#Release_Notes.md'>^ Top</a></p>


---


### Version 3.1.1 ###

New features: Added new Job Posting API related functionality, including the new methods:
  * `postJob()`, `closeJob()`, `editJob()` and `renewJob()`.

Please note that the Job Posting API is a _closed_ API... to use this functionality you must have a Job Posting account with LinkedIn.

Debugging/trouble-shooting: We've added a couple of helpful methods which you can use to access some debugging info via:
  * `lastRequestHeader()`, `lastRequestUrl()`.

Additionally, we've adding some internal data/parameter checking to hopefully catch bad inputs _before_ they are sent to the LinkedIn API.

Full details can be found in the [Change Log](ChangeLog#Version_3.1.1.md)

<p align='right'><a href='ReleaseNotes#Release_Notes.md'>^ Top</a></p>


---


### Version 3.1.0 ###

Version 3.1.0 adds support for the Jobs and Company APIs, including:
  * Company API-specific methods: `company()`, `companyProducts()`, `followCompany()`, `followedCompanies()`, `searchCompanies()`, `suggestedCompanies()`, `unfollowCompany()`.
  * Jobs API-specific methods: `bookmarkJob()`, `bookmarkedJobs()`, `job()`, `searchJobs()`, `suggestedJobs()`, `unbookmarkJob()`.

Additionally, the following changes have been made:
  * Broke the similar functionality of the existing demo script into individual pages, including new demo scripts for the above company and jobs related functionality.
  * The `search()` method, used to perform people searches, has been deprecated and replaced with `searchPeople()` in order to differentiate it from the company and job searches. The deprecated search() method will be removed in a future version of the library.
  * When a throttle limit is reached, the library will report which endpoint returned the throttle limit as part of the throttling exception's message.
  * Demo scripts now support use of non-standard port numbers for those that are running the scripts on different ports.

Full details can be found in the [Change Log](ChangeLog#Version_3.1.0.md)

<p align='right'><a href='ReleaseNotes#Release_Notes.md'>^ Top</a></p>


---


### Version 3.0.2 ###

Small change to the demo script; it was forcing the callback URL to 'http', now supports auto-determination of protocol to support `http`, `https`, etc.

Full details can be found in the [Change Log](ChangeLog#Version_3.0.2.md)


<p align='right'><a href='ReleaseNotes#Release_Notes.md'>^ Top</a></p>


---


### Version 3.0.1 ###

Just a simple change to the authorization workflow, changing the authorization end-point to the 'authenticate' endpoint.

Full details can be found in the [Change Log](ChangeLog#Version_3.0.1.md)

<p align='right'><a href='ReleaseNotes#Release_Notes.md'>^ Top</a></p>


---


### Version 3.0.0 ###

While there haven't been any new features added to the library, we've rolled out version 3.0.0 as a completely new major release due to the following changes:

  * The code has been completely re-factored, including camelCasing the method calls where needed;
  * Streamlined the libraries interaction with the stand-alone OAuth library, and;
  * Increased portability by moving the API tokens outside of the library itself... this allows you, for instance, to make use of the same Simple-LinkedIn file for multiple projects, rather than a single project. This change resulted in a change to the class constructor; please see the demo script and source for more detail.

Other minor enhancements include:

  * Adding an 'oauth' component to the libraries API call responses to aid in debugging:
```
$response = array(
  'info'     => Connection information from cURL,
  'linkedin' => LinkedIn response,
  'oauth'    => The OAuth string and header sent with the request,
  'success'  => Boolean indicating method success
);
```
  * Fixed a bug in the `share()` method related to improper encoding of characters.

As always, have at the [demo site](http://simplelinkedin.fiftymission.net) to see it in action. Let me know if you have any issues.

Full details can be found in the [Change Log](ChangeLog#Version_3.0.0.md)

<p align='right'><a href='ReleaseNotes#Release_Notes.md'>^ Top</a></p>


---


## Version 2 ##

### Version 2.1.0 ###

The latest version of the library makes changes to the `$response` variable from many calls, standardizing them across all methods. Where some methods returned boolean and others an array containing LinkedIn response and connection information, all methods now return an array containing the LinkedIn response, connection information, and a third element containing method/function success.

The format is as follows:

```
$response = array(
  'info'     => Connection information from cURL,
  'linkedin' => LinkedIn response,
  'success'  => Boolean indicating method success
);
```

This was done to enable access to full response data from LinkedIn from all methods, and also to reduce your need to parse and check each LinkedIn response for specific success parameters, such as an HTTP 200 or 201 response. The library handles all of this, allowing you to simplify success verification to:

```
$response = $LINKEDIN->some_action();
if($response['success']) {
  // proceed as needed
} else {
  // handle errors
}
```

Updates to this version:

  1. Added ability to like, unlike, and comment on connection shares via new `like()`, `unlike()`, `likes()`, `comment()`, `comments()` methods;
  1. Per LinkedIn's new data features, implemented system to allow you to specify the format you would like the LinkedIn response in; XML (default), JSON or JSONP.  This is achieved via a call to `LINKEDIN->set_response_format(format)`, where format can be set using the class constants (`LINKEDIN::_RESPONSE_JSON`, `LINKEDIN::_RESPONSE_JSONP`, `LINKEDIN::_RESPONSE_XML`).  The default format, matching the LinkedIn API is XML, and if you wish to use XML you do not need to worry about setting the response type.
  1. Increased method parameter checking and error handling capabilities.
  1. Library now verifies that the conflicting PECL OAuth extension is not installed before instantiating.

Full details can be found in the [Change Log](ChangeLog#Version_2.1.0.md)

<p align='right'><a href='ReleaseNotes#Release_Notes.md'>^ Top</a></p>


---


### Version 2.0.1 ###

Two changes:

  1. Modified `send_request()` to also return the original OAuth request that the library makes.  This can be helpful for debugging API issues, as the response returned now includes:
    * The original OAuth request;
    * The response from LinkedIn, and;
    * The HTTP connection information.
  1. Added a second set on class constants to store 'development' stage application keys.  Setting the new class constant `_API_DEV_MODE` to `TRUE` will make use of these 'development' keys.  Useful for keeping track of what mode/key-pair your application is using, and saves you having to keep two sets of keys in disparate places.

Full details can be found in the [Change Log](ChangeLog#Version_2.0.1.md)

<p align='right'><a href='ReleaseNotes#Release_Notes.md'>^ Top</a></p>


---


### Version 2.0.0 ###

It is recommended that you test your code when upgrading from a previous version of the library as version 2+ changes many method calls and replaces deprecated API methods, such as `update_status()`, with their new equivalents.

  * Overhauled the library, implemented new constructor, method parameters.
  * Added `search()` method that uses the new People Search API.
  * Added `invite()` to send out network invitations by both email and LinkedIn ID.
  * Added `share()` method that uses the new Share API, allowing both sharing and re-sharing.
  * Added `statistics()` method that grabs basic user stats from LinkedIn.
  * Added `static is_id()` method to check format of LinkedIn ID.
  * Integrated `is_throttled()` into every call to LinkedIn, raises an exception if application request has been throttled.

Full details can be found in the [Change Log](ChangeLog#Version_2.0.0.md)

<p align='right'><a href='ReleaseNotes#Release_Notes.md'>^ Top</a></p>


---


## Version 1 ##

### Version 1.2.0 ###

  * Added basic Connections/Messaging API functionality via added `connections()` and `connection_message()` functions.

Full details can be found in the [Change Log](ChangeLog#Version_1.2.0.md)

<p align='right'><a href='ReleaseNotes#Release_Notes.md'>^ Top</a></p>


---


### Version 1.1.1 ###

  * `update_network()` now throws an exception on failure, so you should wrap this call and check for the custom `LinkedInException`:

```
try {
  $response = $LINKEDIN->update_network('Update text');
} catch(LinkedInException $e) {
  // handle exception
}
```

Full details can be found in the [Change Log](ChangeLog#Version_1.1.1.md)

<p align='right'><a href='ReleaseNotes#Release_Notes.md'>^ Top</a></p>


---


### Version 1.1.0 ###

  * Added a static `is_throttled()` function that will check the LinkedIn response and return TRUE/FALSE depending on the throttling state.

Full details can be found in the [Change Log](ChangeLog#Version_1.1.0.md)

<p align='right'><a href='ReleaseNotes#Release_Notes.md'>^ Top</a></p>


---


### Version 1.0.1 ###

  * Fixed a minor bug in the demo script, download the new version and simply overwrite demo.php.

Full details can be found in the [Change Log](ChangeLog#Version_1.0.1.md)

<p align='right'><a href='ReleaseNotes#Release_Notes.md'>^ Top</a></p>


---


### Version 1.0.0 ###

The initial public version of the Simple-LinkedIn class, which wraps LinkedIn API functionality allowing you to connect via PHP.

Currently, you can access the Profile API via the `profile()` method, send a network update via the `update_network` method, and update your status via the `update_status` method.

#### Usage ####

Once you've connected the user of your application to LinkedIn via [OAuth](https://developer.linkedin.com/documents/authentication), you can either change the class constants `_API_KEY` and `_API_SECRET` to contain your API key pair, or you can pass the key pair directly to the class constructor via:

```
$linkedin = new LinkedIn('<your API key>', '<your API secret>');
```

...and then make calls as follows:

```
$response = $linkedin->profile();
```

<p align='right'><a href='ReleaseNotes#Release_Notes.md'>^ Top</a></p>