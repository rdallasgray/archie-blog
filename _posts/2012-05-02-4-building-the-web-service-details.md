---
layout: post
title: "4. Building the Web Service: Details"
description: "venv, pip, foreman, etc."
category: archie
tags: []
date: 2012-05-02 09:51:56
---
{% include JB/setup %}

Heroku uses a number of small tools to make development and deployment easier; first we have to install the [Heroku command line tools](http://devcenter.heroku.com/categories/command-line).

When using Python, dependency management is done using [virtualenv](http://pypi.python.org/pypi/virtualenv) and [pip](http://pypi.python.org/pypi/pip).

Virtualenv creates (as you might guess) a virtual enviroment for running Python applications; all dependencies, including the necessary version of Python itself, exist within this environment.

Pip is used to install and manage dependencies; when using virtualenv, dependency management takes place within the virtual environment. Dependencies, once installed, can be frozen and listed by doing

```
pip freeze > requirements.txt
```

which writes the list of dependencies to a text file.

Once dependencies are taken care of, we next need to tell Heroku how to run our app. This is done by creating a [Procfile](https://devcenter.heroku.com/articles/procfile). The app can then be run using the Ruby tool [Foreman](http://blog.daviddollar.org/2011/05/06/introducing-foreman.html).

Storing the whole shebang in a git repository, we create the application stack on Heroku:

```
heroku create --stack cedar
```

This will also create a git remote called **heroku** -- so it's now simple to push the app to the cloud. Automatically-installed git hooks ensure the app is started as soon as the push is completed. Its state can then be checked by doing

```
heroku ps
```

and any problems traced using

```
heroku logs
```
####Next
Creating the data.
