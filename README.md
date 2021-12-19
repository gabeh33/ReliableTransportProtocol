README.md for Gabe Holmes Project 4 Reliable Transport Protocol 
This project went better for me than the previous project, which was to build a router. I decided to start with Python, since the starter code is in 
Python even if I am more comfortable with Java. The starter code proved very useful, as I was able to get my vm up and code running quickly to start 
writing new code. The first challenge I did was dealing with repeated packets. This was simple, I would just keep track of the sequence numbers on 
the receivers end and if a packet came in with a sequence number that has already been seen, it is ignored. The next challenge was dealing with 
out of order packets. Since the starter code uses a stop and wait method, I am not sure if reordering is even possible. However I wrote some code 
that uses the sequence numbers and the expected sequence number, and this passes the tests so I moved on. The most challenging part of the project
was dealing with dropped packets. I wrote code that would work when the drop rate was small, however I could not figure out how to make it work with 
larger drop rates. The problem, which took me a long time to find, was that I would not resend the end-of-file packet if it got dropped. All the other
data packets I would resend if they got dropped, but the eof packet was outside of the loop so it would only be sent once. Eventually I was able to get 
it to work within the loop, and that along with the receiver sending an ACK when the eof packet is received meant that all the drop cases were handled. 
I tried a lot of different ways to increase the cwnd to more than 1, however I could not get it to work. This means I am passing all but one of the tests,
however overall I feel like I have a lot better understanding of what it is like to deal with an unreliable network. 
