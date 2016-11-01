---
layout: post
title:  "Challenge: Choosing a protocol"
date:   2016-10-28 15:53:04 -0400
categories: CSC_386 Blog New
---

This week the dashboard team had been struggling along with the wifi team to find the simplest way to
send data from the arduino to an API endpoint. We have more or less reached a decision, but it is still 
good to revisit our assumptions. There were three ways in which we though of sending our data each with it's own
advantages and disadvantages.

1. Use JSON to send a POST request
2. Send multiple parameters as a GET request
3. Use the advantage of multiple parametes from flask to send a formed string.
4. Our own Frankestein's monster of a protocol 

The problem that we are facing is one of trade off.
With the arduino we are limited to the amount of RAM that it has, and We are running other things in it.
The plan in order to save battery was:

1. Wake up every so often and take a reading of temperature of the room
2. Store the reading we get in a small C array
3. Send the data when the array is full and start again

The reason that we decided to do this was in order to save the amount of power
that it takes the wifi adapter to wake up and send a request to the server. 

The first idea that we had was to send the information as a JSON POST request. 
This would make it a simple well known structure that would be easy to digest.
This would be the most elegant way to send information and the easiest to unpack for us.
However upon discussion, we found out that the entire string would need to be stored in RAM.
The arduino unfortunately only has 2KB of ram, a very small amount indeed. Each character of the JSON
string would then take up space in our device and the logic to create the string would be as well.
This might prove to be a problem for us and we might run out of RAM and essentially render the device unusable.

The second idea that I personally had was that of sending the information as a GET request.
The get way of sending list as we had invisioned is a bit ugly, but it is less memory consuming and more of
an accepted protocol. The protocol would follow the following format.

**baseurl?deviceName=civet&readings=value1&readings=value2**

With a long array this string can get a bit out of hand though and we will run into the same problems as we 
would with a JSON protocol.

The third way that we though of sending this data is to use the flask parameters.
A flask parameter can be thought of a function parameter if follows the following convention

/&lt;parameter&gt; 

so we could form as string similar to the get request.

/&lt;key&gt;/&lt;tag&gt;etc..

This however fall under the same disadvantage as those above. 

Finally we spoke of a Frankestein's monster protocol. One that we came up with ourselves. 
The idea is that we would know how big the readings are and thus we can pass them as one big string parameter

/&lt;key&gt;/&lt;allthereadings&gt;

This might work, but I can imagine it being a complete mess in terms of readability and maintainability.


Due to this we decided on the simplest of solutions. Using a one sensor one reading approach.
This will consists of a url that passes in the tag value and reading type. This might kill the battery in the arduino, 
but it might be the best that we can do for now.

