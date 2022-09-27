# Authentication and Hard Algorithms

Most people know that Bitcoin is hard to mine. If you want to mine Bitcoin would take a long time to do so on your computer.
In fact, you might not even finish! This is by design. If everone could mine Bitcoin, it wouldn't be worth anything.
It wouldn't be money. If you want to store something valuable, like a password, you want to do it in a way that would
require someone spending a long time on a computer trying to find it out. In fact, you hope they would never finish!

Bcrypt and other algorithms take a string of characters, 
like a password and return a (fairly) unique string of characters that are keyed to the original string.
That is, if you were to run the process again, you would get the same (fairly) unique string of characters out.
But, it is very hard to guess the original string. It can be done, but it would take a very, very long time.
You probably won't finish! But, creating the (fairly) unique string that is keyed to an original string (like a password)
is very fast! So we can do it fast if we know the password. But they can't get the password back even if they see the (fairly) unique string of characters that is keyed to the original!

# Basic Authentication

Basic Authentication is OK. But there are better ways that are just as easy to implement.

In BA, the user submits the password with every request. This can be done automatically by the browser by saving the password for the user.
You may be wondering why this is a problem. Well, it makes us nervous if your password is transmited more often than it needs to be.
If an attacker gets the password, there is no other way for a web admin to tell that you are really you.
A better way is to create a temporary passcode to pass back and forth. 
That way, even if you are lax about security at the coffee shop, the worst that can happen (hopefully) is someone can highjack the current session. 
But they can't sleep on in and log in as you latter because that session will just expire when you logout.
