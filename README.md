# StrawPy 1.1

StrawPy is a python wrapper for [Strawpoll](http://www.strawpoll.me/).

# Table of Contents

+ [Obtaining StrawPy](#obtaining-strawpy)
+ [Using StrawPy](#using-strawpy)
	+ [Get Poll](#get-poll)
	+ [Create Poll](#create-poll)
	+ [StrawPoll Class](#strawpoll-class)
+ [Changelog](#changelog)
+ [Attribution](#attribution)
+ [License](#license)

# Obtaining StrawPy

You can get StrawPy using pip install:

	pip install strawpy
	
OR:

Going [here](https://github.com/EricDalrymple91/strawpy) :octocat:, downloading the zip file and running the setup file:

	python setup.py install

# Using StrawPy

You can get a response from an existing poll or create a new one using Strawpy.

```python
import strawpy

```

### Get Poll

Send a get request to the Strawpoll API based on a poll ID. Returns a [StrawPoll](#strawpoll-class) class object.

:page_with_curl: Example:

```python
poll = strawpy.get_poll('11682852')

```

### Create Poll

Send a post request to the Strawpoll API based poll data parameters. Returns a [StrawPoll](#strawpoll-class) class object.

:page_with_curl: Example:

```python
new_poll = strawpy.create_poll('Is Python the best?', ['Yes', 'No'])

```
### StrawPoll Class

A strawpy.StrawPoll class is returned from a successful get_poll or create_poll function.

:green_book: Attributes:

* id
* title
* votes
* options
* captcha
* dupcheck
* results
* results_with_percent
* url
* results_url

:orange_book: Methods:

* open(results=False)
* refresh()

:page_with_curl: Example:

```python
poll = strawpy.get_poll('11682852')

print poll
print poll.id
print poll.title
print poll.votes
print poll.options
print poll.captcha
print poll.dupcheck
print poll.results
print poll.results_with_percent
print poll.url
print poll.results_url
poll.refresh()
poll.open(results=False)

```

# Changelog

### 1.1 (2016-12-7)

:wrench: Features:

- Added url attribute to StrawPoll class objects.
- Added results_url to StrawPoll class objects.
- Added refresh method to StrawPoll class objects.

### 1.0 (2016-11-18)

:notebook: Notes:

- Initial release.

# Attribution

StrawPy isn't endorsed by [Strawpoll](http://www.strawpoll.me/) and doesn't reflect the views or opinions of Strawpoll or anyone officially involved in producing or managing Strawpoll or the Strawpoll API. 

# License

The MIT License (MIT)
