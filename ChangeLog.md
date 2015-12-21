# Change Log #

A complete list of all changes to the Simple-LinkedIn library.



<p align='right'></p>


---


## Version 3 ##

### Version 3.3.0 ###

#### Core ####

##### New #####

  * Added `_URL_AUTHORIZE` class constant, which points to the LinkedIn authorize endpoint. See [issue 12](https://code.google.com/p/simple-linkedinphp/issues/detail?id=12) for the original enhancement suggestion.
  * Added `createPostComment()` method, used to add a comment on a group post.
  * Added `deletePostComment()` method, used to delete a comment on a group post.
  * Added `exchangeToken()` method, used to exchange an OAuth 2.0 bearer token for a permanent OAuth 1.0 token.
  * Added `unfollowPost()` method, used to unfollow a group post.
  * Added `unlikePost()` method, used to unlike a group post.

##### Changes #####

  * Changed `_API_OAUTH_REALM` class constant to `_DEFAULT_OAUTH_REALM`.
  * Changed `_API_OAUTH_VERSION` class constant to `_DEFAULT_OAUTH_VERSION`.
  * Changed and deprecated `_URL_AUTH` class constant to `_URL_AUTHENTICATE` to better differentiate it from the new `_URL_AUTHORIZE` class constant.
  * Changed `followPost()` method, removing the ability to use it to unfollow a particular post. Use the new `unfollowPost()` method to do this.
  * Changed `likePost()` method, removing the ability to use it to unlike a particular post. Use the new `unlikePost()` method to do this.
  * Renamed and deprecated private `checkResponse()` method to `setResponse()`.
  * Changed `setResponse()` method from using PHP 5.3.x supported closures. No uses a simple iteration allowing for use with PHP < 5.3.x. See [issue 11](https://code.google.com/p/simple-linkedinphp/issues/detail?id=11) for more details.
  * Renamed and deprecated `comment()` method to `createUpdateComment()` to clarify it's use with network updates.
  * Renamed and deprecated `comments()` method to `updateComments()` to clarify it's use with network updates.
  * Renamed and deprecated `like()` method to `likeUpdate()` to clarify it's use with network updates.
  * Renamed and deprecated `likes()` method to `updateLikes()` to clarify it's use with network updates.
  * Renamed and deprecated `unlike()` method to `unlikeUpdate()` to clarify it's use with network updates.

##### Miscellaneous #####

  * Added new internal data checking to class constructor.
  * Added additional cURL response checking in `fetch()` method.
  * Removed addition of unnecessary headers in `fetch()` method.
  * Updated PHPDoc comments.

#### Demo ####

##### New #####

  * Added tokenExchange.html and tokenExchange.php scripts, demonstrating new `exchangeToken()` method.

<p align='right'><a href='ChangeLog#Change_Log.md'>^ Top</a></p>


---


### Version 3.2.0 ###

#### Core ####

##### New #####

  * Added `createPost()` method, used to create a post.
  * Added `deletePost()` method, used to delete a previous post by the user.
  * Added `flagPost()` method, used to flag a specific post.
  * Added `followPost()` method, used to follow a specific post.
  * Added `group()` method, used to retrieve detailed information about a specific group.
  * Added `groupMemberships()` method, used to retrieve a user's group memberships.
  * Added `groupPost()` method, used to retrieve detailed information about a specific post.
  * Added `groupPostComments()` method, used to retrieve all the comments for a post.
  * Added `groupPosts()` method, used to retrieve all the posts in a group.
  * Added `groupSettings()` method, used to retrieve the settings for a group.
  * Added `joinGroup()` method, used to join a group.
  * Added `leaveGroup()` method, used to leave a group the user is a member of.
  * Added `likePost()` method, used to 'like' a post.
  * Added `raw()` method, allowing for manual calls to the API for unimplemented functionality to be accessed.
  * Added `removeSuggestedGroup()` method, used to remove a group fro the suggested group list from LinkedIn.
  * Added `setGroupSettings()` method, used to change the settings of a group the user administrates.
  * Added `suggestedGroups()` method, used to retrieve LinkedIn's suggested groups for the user.

#### Demo ####

##### New #####

  * Added groups.php script, demonstrating new groups related methods.
  * Moved all demo scripts to HTML5.

<p align='right'><a href='ChangeLog#Change_Log.md'>^ Top</a></p>


---


### Version 3.1.1 ###

#### Core ####

##### New #####

  * Added private `checkResponse()` method, used internally to centralize verification of the response from LinkedIn.
  * Added `closeJob()` method, used to close jobs that the user has previously posted - this can only be used with the private Job Posting API.
  * Added `editJob()` method, used to edit jobs that the user has previously posted - this can only be used with the private Job Posting API.
  * Added `lastRequestHeader()` debugging/informational method, used to retrieve the last header passed by the class to LinkedIn.
  * Added `lastRequestUrl()` debugging/informational method, used to retrieve the last URL used by the class to communicate with LinkedIn.
  * Added `postJob()` method, used to post jobs - this can only be used with the private Job Posting API.
  * Added `renewJob()` method, used to renew jobs that the user has previously posted - this can only be used with the private Job Posting API.

##### Miscellaneous #####

  * Added internal data/parameter checking to all methods.

#### Demo ####

##### New #####

  * Added jobsPosting.php script, demonstrating new jobs posting related methods.

<p align='right'><a href='ChangeLog#Change_Log.md'>^ Top</a></p>


---


### Version 3.1.0 ###

#### Core ####

##### New #####

  * Added `bookmarkJob()` method, used to bookmark an existing job.
  * Added `bookmarkedJobs()` method, used to retrieve a user's bookmarked jobs.
  * Added `company()` method, used to retrieve detailed information about a specific company.
  * Added `companyProducts()` method, used to retrieve the products of a specific company.
  * Added `followCompany()` method, used to follow a company.
  * Added `followedCompanies()` method, used to retrieve a user's followed companies.
  * Added `job()` method, used to retrieve detailed job information.
  * Added `searchCompanies()` method, used to search companies on LinkedIn.
  * Added `searchJobs()` method, used to search jobs on LinkedIn.
  * Added `searchPeople()` method, used to search people on LinkedIn.
  * Added `suggestedCompanies()` method, used to retrieve LinkedIn's suggested companies for the user.
  * Added `suggestedJobs()` method, used to retrieve LinkedIn's suggested jobs for the user.
  * Added `unbookmarkJob()` method, used to unbookmark an existing job.
  * Added `unfollowCompany()` method, used to unfollow a company.

##### Changes #####

  * Deprecated `search()` method, replaced by `searchPeople()`. The deprecated search() method will be removed in a future version of the library.
  * Protected `fetch()` method modified, with throttle-triggered exception now reporting the endpoint that has triggered a throttle limit.

#### Demo ####

##### New #####

  * Added company.php script, demonstrating new company related methods.
  * Added new jobs.php script, demonstrating new jobs related methods.
  * Added new content.php script, moving existing content related functionality from the base demo.php script.
  * Added new network.php script, moving existing network related functionality from the base demo.php script.

##### Changes #####

  * Demo scripts now support use of non-standard port numbers for those that are running the scripts on different ports. See [issue 6](https://code.google.com/p/simple-linkedinphp/issues/detail?id=6) for details.
  * Demo scripts now check that sessions have been enabled on the local server, a requirement for the demo scripts to work. See [issue 7](https://code.google.com/p/simple-linkedinphp/issues/detail?id=7) for more details.

<p align='right'><a href='ChangeLog#Change_Log.md'>^ Top</a></p>


---


### Version 3.0.2 ###

#### Demo ####

##### Miscellaneous #####

  * Changed demo script from hard-coded `http` callback protocol to use protocol auto-determination, supporting both `http` and `https`. See [issue 4](https://code.google.com/p/simple-linkedinphp/issues/detail?id=4) for details.

<p align='right'><a href='ChangeLog#Change_Log.md'>^ Top</a></p>


---


### Version 3.0.1 ###

#### Core ####

##### Miscellaneous #####

  * Updated `_URL_AUTH` class constant, changing to the new 'authenticate' endpoint that allows for automatic authentication in certain circumstances. See this [LinkedIn Developer's Blog](https://developer.linkedin.com/blog/) [entry](https://developer.linkedin.com/blog/oauth-now-authentication) for more details.

<p align='right'><a href='ChangeLog#Change_Log.md'>^ Top</a></p>


---


### Version 3.0.0 ###

#### Core ####

##### New #####

  * Added private `fetch()` method, used to send all requests to the OAuth library.

**Changes**

  * Renamed all existing methods to their camel case equivalent, e.g. `is_id()` -> `isId()`.
  * Moved all class interaction with the stand-alone OAuth library to the new `fetch()` method.
  * Modified the class constructor, now taking in a single array parameter that contains the application API keys.
  * Modified `share()` method, fixing a bug related to improper encoding of characters.
  * Removed `_API_KEY`, `_API_SECRET`, `_API_DEV_MODE`, `_API_DEV_KEY`, `_API_DEV_SECRET` class constants, moving the determination of application keys to outside of the library so that multiple applications can use the same install.
  * Modified the returned values from all methods, adding an `'oauth'` component to the libraries API call responses to aid in debugging:

```
$response = array(
  'info'     => Connection information from cURL,
  'linkedin' => LinkedIn response,
  'oauth'    => The OAuth string and header sent with the request,
  'success'  => Boolean indicating method success
);
```

<p align='right'><a href='ChangeLog#Change_Log.md'>^ Top</a></p>


---


## Version 2 ##

### Version 2.1.0 ###

#### Core ####

##### New #####

  * Added `comment()` method, used to post a comment on a network share.
  * Added `comments()` method, used to retrieve all the comments on a given network share.
  * Added `like()` method, used to like a network share.
  * Added `likes()` method, used to retrieve the likes on a given network share.
  * Added `set_response_format()` method, used to set the data format of the LinkedIn response.
  * Added `unlike()` method, used to unlike a previously liked network share.
  * Added `_RESPONSE_JSON` class constant, used in conjunction with `set_response_format()` to set the data response from LinkedIn to JSON.
  * Added `_RESPONSE_JSONP` class constant, used in conjunction with `set_response_format()` to set the data response from LinkedIn to JSONP.
  * Added `_RESPONSE_XML` class constant, used in conjunction with `set_response_format()` to set the data response from LinkedIn to XML. This is the default setting.
  * Added existence check for PECL OAuth extension - class will throw an exception if it is found, as it conflicts with the required stand-alone OAuth library required by the class. See [issue 1](https://code.google.com/p/simple-linkedinphp/issues/detail?id=1) for more details.

##### Changes #####

  * Modified the returned values from all methods, standardizing the response to the following format:

```
$response = array(
  'info'     => Connection information from cURL,
  'linkedin' => LinkedIn response,
  'success'  => Boolean indicating method success
);
```

##### Miscellaneous #####

  * Added internal data/parameter checking to key methods.

<p align='right'><a href='ChangeLog#Change_Log.md'>^ Top</a></p>


---


### Version 2.0.1 ###

#### Core ####

##### New #####

  * Added `_API_DEV_MODE` class constant, which is set to `TRUE`, will use the two new 'development' API application key class constants.
  * Added `_API_DEV_KEY` class constant, used to store the 'development' API application key.
  * Added `_API_DEV_SECRET` class constant, used to store the 'development' API application secret.

##### Changes #####

  * Modified `send_request()` method to return the original OAuth request that the class sends to LinkedIn.

<p align='right'><a href='ChangeLog#Change_Log.md'>^ Top</a></p>


---


### Version 2.0.0 ###

#### Core ####

##### New #####

  * Added `invite()` method, used to send out network invitations by both email and LinkedIn member token.
  * Added static `is_id()` method, used to check format of a given LinkedIn member token.
  * Added `search()` method, used to search people on LinkedIn.
  * Added `share()` method, used to share and re-share content.
  * Added `statistics()` method, used to retrieve the current user's network graph.

##### Changes #####

  * Refactored code, implemented new constructor with additional parameters.

##### Miscellaneous #####

  * Integrated `is_throttled()` method into every call to LinkedIn, raises an exception if application request has been throttled.

<p align='right'><a href='ChangeLog#Change_Log.md'>^ Top</a></p>


---

## Version 1 ##

### Version 1.2.0 ###

#### Core ####

##### New #####

  * Added `connections()` method, used to retrieve LinkedIn user connections.
  * Added `connection_message()` method, used to send messages from the current user to their connections.

<p align='right'><a href='ChangeLog#Change_Log.md'>^ Top</a></p>


---


### Version 1.1.1 ###

#### Core ####

##### Changes #####

  * Added exception checking to `update_network()` method.

<p align='right'><a href='ChangeLog#Change_Log.md'>^ Top</a></p>


---


### Version 1.1.0 ###

#### Core ####

##### New #####

  * Added static `is_throttled()` method, used to check the LinkedIn response and return TRUE/FALSE depending on the throttling state.

<p align='right'><a href='ChangeLog#Change_Log.md'>^ Top</a></p>


---


### Version 1.0.1 ###

#### Demo ####

##### Changes #####

  * Minor changes to the demonstration script.

<p align='right'><a href='ChangeLog#Change_Log.md'>^ Top</a></p>


---


### Version 1.0.0 ###

#### Core ####

##### New #####

  * Base class created and published.

<p align='right'><a href='ChangeLog#Change_Log.md'>^ Top</a></p>