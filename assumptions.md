# The hair pulling problem (or check your assumptions)

> Aarg!!!

The cry of frustration was clearly heard in the dev room

> What’s up?

> I have been pouring over this bug for an hour in my web page  and I can’t figure out what is wrong!

> What’s the bug?

> I must have done something wrong but I can’t find what. This page should show this collection of things that it’s loading from the server but its not showing everything. Only five items are showing and i can’t figure out why. 

> What have you tried?

> I was thinking maybe it was a css thing with overflow hidden, or a float. Or maybe the data binding was wrong, or some property is set that makes things hidden in some of the event handlers, or the data parsing...

> Ok I see. There are a lot of moving parts and we don’t know where the problem is. Let’s Divide and Conquer

> What?

> When dealing with a bigger problem you need to break it down into smaller parts. That way you can deal with smaller issues methodically instead of just jumping around. 

> Ok, makes sense but where do I start?

> Check your assumptions

> Huh?

> You have already been looking at the most obvious problem areas. Now it is time to check your assumptions. 

> What do you mean?

> You are assuming that you are getting some data from the server and the problem is in the web page. Are you sure you are getting the data you want from the server? Use the browser developer tools , Fiddler, postman or any other tool  to check what data you are actually getting from the server.

> Hmmm, that’s strange. I’m only getting five items… But why?

> Well maybe there is some server side paging, or wrong parameters or a bug in the backend. But now you know where the problem is.

> So I just spent an hour chasing ghosts?

> Hindsight is always 20/20 but it helps to really focus on what you know, challenge your assumptions and Divide and Conquer