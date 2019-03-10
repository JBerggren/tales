# The hair pulling problem (or check your assumptions)

> Aarg!!!

The cry of frustration was clearly heard in the dev room

> What’s up?

> I have been pouring over this bug for an hour in my web page  and I can’t figure out what is wrong!

> What’s the bug?

> I must have done something wrong but I can’t find what. This page should show this collection of things that it’s loading from the server but its not showing everything. Only five items are showing and i can’t figure out why. 

> What have you tried?

> I was thinking maybe it was a css thing with overflow hidden. Then I was thinking that maybe the data binding was wrong, or some property is set that makes things hidden in some of the event handlers. Maybe its the the data parsing...

> Ok I see. There are a lot of different parts involved and you have been testing some things on different levels. You need to divide the problem in smaller parts to narrow down where the actual problem is. Divide and Conquer.   

> Ok, but where do I start?

> Let's start from the bottom and challenge your assumption.

> What do you mean?

> You are assuming that you are getting some data from the server and the problem is in the web page. Let's challenge that assumption: Are you sure you are getting the data you want from the server? 

> I think so...

> Well let's be sure. Use the browser developer tools , Fiddler, postman or any other tool  to check what data you are actually getting from the server.

> Hmmm, that’s strange. I’m only getting five items… But why?

> Well maybe there is some server side paging, or wrong parameters or a bug in the backend. But now you know where the problem is.

> So I just spent an hour chasing ghosts in the web page?

> Hindsight is always 20/20 but it helps to really focus on what you know and challenge your assumptions