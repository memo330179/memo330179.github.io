---
layout: post
title:  "Progress: Creating a Dash"
date:   2016-10-28 15:53:04 -0400
categories: CSC_386 Blog New
---
This week we have accomplished a couple of things in our project.
1. We are saving into a database.
2. We are sending emails.

Both of these accomplishments allow us to get a bit further into our project.
By saving into a database we fulfill one of the requirements that we had for the sensor
to be deployed at pine mountain and that that the information be kept on campus. We have tested
our application on a pi setup on campus. Saving into a database will help us do the rest of the things
that we need to do.

The flow of the application will most likely be as follows.
The sensor will request a page on the server.

```python
"/<key>/<tag>/<value>"
```
this will allow our page to insert to the database and have the latest record of the temperature.
It will also check to make sure that the temperature is within the proper range.
If it finds that it is not then it will email the people responsible. It will email to their emails,
but also to their phones. Sending to a 1234567891@tmobile.com for example send to a mobile device.
This will come in handy and will cut cost.

