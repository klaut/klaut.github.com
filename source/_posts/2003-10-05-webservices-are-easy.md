---
layout: post
title: Webservices are easy
tags:
- Actionscript
status: publish
type: post
published: true
meta:
  _oembed_f55bd029ce0af121b94f72c14bd1f15b: ! '{{unknown}}'
  _oembed_1c24c178bdb6d09e4a23da8fa0335032: ! '{{unknown}}'
---
Just out of curiosity i tried the webserviceConnector component. I really wanted to see if it really is that simple to set up and use (as everybody is saying)...
And, honestly, it took me 15 minutes to make it (5 minutes were spent on deciding which webservice i'm going to use).
Knowing that <a href="http://www.webservicex.net/ws/default.aspx">WebserviceX.Net</a> have recently put a crossdomain policy file up on their server, i tried my luck with their leingth/distance converter:
http://www.webservicex.net/length.asmx?WSDL

<a href="http://www.klaustrofobik.org/blog/stuff/webservice_LengthConverter.html">Preview the service here</a>

All you have to do is to open web service window (Window/developer Panels/Web Services), click on Define web service icon (that thing that looks like Earth) and type the url of the service in the pop up window. After a while (when flash connects to the service and recieves back the response) all the methods aviable from this service will be listed in that window. Now its' only a matter of selecting which one you want to use, right click on it and select "Add method call" and flash will automatically place an instance of WebserviceConnector component on the stage.
I also added a couple of comboboxes (for the unit names), a textInput , a textArea (which will display a result from the conversion) and a button on the stage.
The trickiest part now is to bind the webserviceConnector to other components on stage. Ok, it sounds tricky, but it really is not ;)
Select the webserviceConnector and click on the bindings tab in the Component Inspector panel and add your bindings (click on the +)... I added the simplest one first, the result that the service will send me. I selected it (the last one, called results:Number) and then set the "bound to" to point to my textArea component (more preciselly, its text property). I did the same with other parameters:
params.LengthValue - bounded to textInput field:text
params.fromLengthUnit - bounded to fromLengthUnit_combobox:value
params.toLengthUnit - bounded to toLengthUnit_combobox:value

now, what's left is just few lines of code: we want to trigger the service when we click on the button, so we have to write an event handler for that:
<code>
goConvert = function (ev)
{
//ChangeLength_wbs is the instance name of the webservice component
	ChangeLength_wbs.trigger();
};

convertButton_pb.addEventListener("click", goConvert);

</code>

Attached is a zipped fla for taking a closer look :)

<a href="http://www.klaustrofobik.org/blog/stuff/webservice_LengthConverter.zip">Download zipped file</a>


UPDATE:
Just noticed that <a href="http://www.mediasparkles.com/2003_10_05_archives.html#106537575512611530">Vera Fleischer</a> has written a great in-depth post on how to use webserviceConnector :)
