random notes

I work in IT at a fairly large bank. The other day I was trying to get some user
's desk location, hard to see in the Corporate online directory, and started playing with some Python LDAP code. Out of curiosity, rather than continue with LDAP queries, I ran a "*" query, got everyone's info, and awk'd it in to a simple JSON format file.
 
Taking that file, I copied it into an index.html file, with a simple query form, and quickly had a full regular expression name query set up. While the bank is big enough, the whole JSON info is only some 6 MB, so the page loads in under 1/3 second. Simple regex queries over the data take 2-4 milliseconds.
 
None of that is the point of this essay. What's slightly interesting here, and what I want to talk about, is that this file is not served by a node server or tomcat container or python or go or docker. It's just a file. We happen to have a decent corporate distributed file system, and while this isn't in the production network, anyone anywhere in the bank can get to the index.html file and perform queries.
 
So I showed this to a couple people and the first reaction is "Cool!". They were a little impressed - though in IT we're loathe to show it - that the searches took single-digit milliseconds.
 
That is, they were a little impressed until I explained that there weren't any servers or services running, just the file loaded index.html. Given that there weren't any interesting micro-services running or frameworks, no indexing, practically no modern tech stack at all, their reactions turned a little cold.
 
You see, getting data delivered throughout an enterprise using files isn't "Cool
". Files are boring, they don't scale, no one wants to talk about files.
 
And that's what I want to talk about.
 
The Cloud That Was and The Post-POSIX world of Today
 
Now, my little demo app doesn’t scale to the internet; on the other hand, the company I’m at isn’t too big and never will be. The services available – Corporate Directory and LDAP – are slow, cumbersome, either closed off or arcane. My analysis was that rather than  In fact, anyone can get to the 'raw' JSON data and query that, or, gosh, even grep it. 
 
Mostly about AFS - The Cloud That Was.

