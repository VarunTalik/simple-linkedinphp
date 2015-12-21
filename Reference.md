# Reference (by LinkedIn API) #

Simple-LinkedIn class reference, with methods organized by LinkedIn API.



<p align='right'></p>


---


## Company API ##

Implements the [Company API](https://developer.linkedin.com/documents/company-lookup-api-and-fields), [Company Follow API](https://developer.linkedin.com/documents/company-follow-and-suggestions) and [Company Products API](https://developer.linkedin.com/documents/company-products-and-recommendations):

  * `public function company($options, $by_email = FALSE)`

### Follow ###

  * `public function followCompany($cid)`
  * `public function followedCompanies()`
  * `public function suggestedCompanies()`
  * `public function unfollowCompany($cid)`

### Products ###

  * `public function companyProducts($cid, $options = '')`

<p align='right'><a href='Reference#Reference_(by_LinkedIn_API).md'>^ Top</a></p>


---


## Company Search API ##

Implements the [Company Search API](https://developer.linkedin.com/documents/company-search):

  * `public function searchCompanies($options = '')`

<p align='right'><a href='Reference#Reference_(by_LinkedIn_API).md'>^ Top</a></p>


---


## Connections API ##

Implements the [Connections API](https://developer.linkedin.com/documents/connections-api):

  * `public function connections($options = '~/connections')`

<p align='right'><a href='Reference#Reference_(by_LinkedIn_API).md'>^ Top</a></p>


---


## Groups API ##

Implements the [Groups API](https://developer.linkedin.com/documents/groups-api):

  * `public function group($gid, $options)`

### Settings ###

  * `public function groupSettings($gid, $options = '')`
  * `public function setGroupSettings($gid, $xml)`

### Membership ###

  * `public function groupMemberships($options = '')`
  * `public function joinGroup($gid)`
  * `public function leaveGroup($gid)`

### Suggestions ###

  * `public function removeSuggestedGroup($gid)`
  * `public function suggestedGroups()`

### Posts ###

  * `public function groupPost($pid, $options = '')`
  * `public function groupPosts($gid, $options = '')`

#### Manage ####

  * `public function createPost($gid, $title, $summary = '')`
  * `public function deletePost($pid)`

#### Comments ####

  * `public function createPostComments($pid, $comment)`
  * `public function deletePostComments($cid)`
  * `public function groupPostComments($pid, $options = '')`

#### Flag ####

  * `public function flagPost($pid, $type)`

#### Follow ####

  * `public function followPost($pid)`
  * `public function unfollowPost($pid)`

#### Like ####

  * `public function likePost($pid)`
  * `public function unlikePost($pid)`

<p align='right'><a href='Reference#Reference_(by_LinkedIn_API).md'>^ Top</a></p>


---


## Invitation API ##

Implements the [Invitation API](https://developer.linkedin.com/documents/invitation-api):

  * `public function invite($method, $recipient, $subject, $body, $type = 'friend')`

<p align='right'><a href='Reference#Reference_(by_LinkedIn_API).md'>^ Top</a></p>


---


## Job API ##

Implements the [Jobs API](https://developer.linkedin.com/documents/job-lookup-api-and-fields):

  * `public function job($jid, $options = '')`

### Bookmarks ###

  * `public function bookmarkJob($jid)`
  * `public function bookmarkedJobs()`
  * `public function unbookmarkJob($jid)`

### Suggestions ###

  * `public function suggestedJobs($options = ':(jobs)')`

<p align='right'><a href='Reference#Reference_(by_LinkedIn_API).md'>^ Top</a></p>


---


## Job Posting API ##

Implements the private Job Posting API:

  * `public function postJob($xml)`

### Manage ###

  * `public function closeJob($jid)`
  * `public function editJob($jid, $xml)`
  * `public function renewJob($jid, $cid)`

<p align='right'><a href='Reference#Reference_(by_LinkedIn_API).md'>^ Top</a></p>


---


## Job Search API ##

Implements the [Job Search API](https://developer.linkedin.com/documents/job-search-api):

  * `public function searchJobs($options = '')`

<p align='right'><a href='Reference#Reference_(by_LinkedIn_API).md'>^ Top</a></p>


---


## Messaging API ##

Implements the [Messaging API](https://developer.linkedin.com/documents/messaging-between-connections-api):

  * `public function message($recipients, $subject, $body, $copy_self = FALSE)`

<p align='right'><a href='Reference#Reference_(by_LinkedIn_API).md'>^ Top</a></p>


---


## Network Updates API ##

Implements the [Network Updates API](https://developer.linkedin.com/documents/get-network-updates-and-statistics-api):

  * `public function updates($options = NULL, $id = NULL)`
  * `public function updateNetwork($update)`

### Comments ###

  * `public function createUpdateComment($uid, $comment)`
  * `public function updateComments($uid)`

### Likes ###

  * `public function likeUpdate($uid)`
  * `public function updateLikes($uid)`
  * `public function unlikeUpdate($uid)`

<p align='right'><a href='Reference#Reference_(by_LinkedIn_API).md'>^ Top</a></p>


---


## People Search API ##

Implements the [People Search API](https://developer.linkedin.com/documents/people-search-api):

  * `public function searchPeople($options = NULL)`

<p align='right'><a href='Reference#Reference_(by_LinkedIn_API).md'>^ Top</a></p>


---


## Profile API ##

Implements the [Profile API](https://developer.linkedin.com/documents/profile-api):

  * `public function profile($options = '~')`

<p align='right'><a href='Reference#Reference_(by_LinkedIn_API).md'>^ Top</a></p>


---


## Share API ##

Implements the [Share API](https://developer.linkedin.com/documents/share-api):

  * `public function share($action, $content, $private = TRUE, $twitter = FALSE)`

<p align='right'><a href='Reference#Reference_(by_LinkedIn_API).md'>^ Top</a></p>


---


## Statistics API ##

Implements the [Statistics API](https://developer.linkedin.com/documents/get-network-updates-and-statistics-api):

  * `public function statistics()`

<p align='right'><a href='Reference#Reference_(by_LinkedIn_API).md'>^ Top</a></p>


---


## Token Exchange API ##

Implements the [Token Exchange API](http://developer.linkedin.com/documents/exchange-jsapi-tokens-rest-api-oauth-tokens):

  * `public function exchangeToken($bearer_token)`

<p align='right'><a href='Reference#Reference_(by_LinkedIn_API).md'>^ Top</a></p>

## Miscellaneous ##

  * `public static function isId($id)`
  * `public static function isThrottled($response)`
  * `public function lastRequestHeader()`
  * `public function lastRequestUrl()`
  * `public function raw($method, $url, $body = NULL)`
  * `public function retrieveTokenAccess($token, $secret, $verifier)`
  * `public function retrieveTokenRequest()`
  * `public function revoke()`
  * `public function setResponseFormat($format = self::_DEFAULT_RESPONSE_FORMAT)`
  * `public function setToken($token)`
  * `public static function xmlToArray($xml)`

<p align='right'><a href='Reference#Reference_(by_LinkedIn_API).md'>^ Top</a></p>