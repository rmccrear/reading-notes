# Reading notes on Express and Middleware

## Express and Middleware

Each page, or route, of a server usually does just one thing. 
One page may show a list of all your friends.
One may show a list of all recent messages.
Another may allow you to change your settings.
Or post a new message.

But each of these may have something in common. Maybe they all require you to be logged in.
There are some pages that can be grouped by what they have in common. For example, some pages require some sort of user input other than just clicking a link. A form with text could be submitted.

All the pages that require the user to be logged in require the programmer to check if the user is logged in. To make things easier, the programmer can choose middleware to make the job easier.
The middleware can check automatically whether or no the user is logged in, and redirect to the loggin page if not. Or, middleware could check to see if all form input from the user came from a page that was recently requested by the user so as to avoid malicious activity.

Middleware makes all of these chores easier to manage for programers so we can concentrate on the on thing that is done by the page at hand.

Express is perhaps the most popular framework for creating severs. It is "unopinionated" which means there are many ways to do the same thing.
Often this means we have to do things ourselves that would otherwise be taken care of in a more "batteries-included" framework. 
However, we can use modules to make developing servers faster and easier. In fact sometimes modules have their own modules that plug in. The may even require them.
So we can compose a piece of software by putting together modules in more-or-less standard or more-or-less unique ways. 


## NPM

NPM can help with organizing modules, including middleware. 
There are libraries providing middleware that helps check the validity of user input, 
or ensure that we can tell if a user is really logged in or not.
Re-implementing these tasks for each project would mean less projects being finished and more security problems. 
So we use NPM to manage and share libraries accross the Node.js ecosystem.

# TDD and tests

## TDD

Tests are useful for programmers. All programmers do tests even if they don't write them down in a `test` folder.
Tests help us check if a program "works" and runs correctly. The even help us to define what "correct" means in a given context.
Some people think tests are so wonderful, our development should be driven by tests. That is, write test, then write code that passes the tests.
This line of thinking falls under TDD, or Test-Driven-Development.

Some programmers don't like writing tests. They are cumbersome and sometimes take longer to write, and get right than the program they are testing.
They also need to change to keep up with changes in the code or the design of the program. 
But they have benefits. 
You may find flaws in the program that you may have missed, finding it when the code is fresh in your mind, 
instead of much later so you have to hunt for it, which wastes much more time.

Some ways to avoid problems with tests are remembering to run tests frequently to avoid the tests getting out of data, and not writing tests that are too detailed or tedious.

Teams may run into problems if some team members write tests, but others don't. 
If a team member changes code that breaks test. It will cause problems for other team members to clean up. 
This may even lead to a test suite being abandoned because it doesn't pass anymore and it is hard to tell which tests are still relevant.

## CI/CD

Continuous Integration (CI) is a name for a sytem of tools that continuously check if new code work properly no matter who in a team commits it.
It relies on a test suite to indicate whether or not the newly commited code is good or bad, 
so it is important to have complete and up-to-date tests for this system to work properly.
Since it runs tests everytime a new commmit is integrated into the code base, the tests won't go stale and bugs can be caught earlier.
It also makes it easier to merge code because the tests run autonomously. 
Since commits can be made more frequently, they can be smaller, and conflicts will be easier to unravel.

Continuous Deployment (CD) is possible with CI because the code is checked out by the CI process and can go directly into production and be deployed.

Github has tools to help with CI/CD. 
Github actions can run tests on every commit and a hook can be created to tell your deployment system to redeploy new 
code everytime the main code repository branch is updated.








