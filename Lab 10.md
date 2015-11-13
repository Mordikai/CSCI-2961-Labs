#Lab 10 Group Writeup
####Group Members
Ehsan Ahmed &
Max Walker
###Part 1
We loaded up the drivers, and compiled and ran the Blink example. Fiddling around with the timing was a simple matter of changing the delays within the loop. The board seems to work fine, and our settings are in order to comtinue onwards.
###Part 2
After some confusion over a compilation error, we loaded the Hello World program. No real hitches here.
###Part 3
We took a while on this one. Got way too occupied with cstring manipulation. Eventually realized that we should be working with the arduino String library, whaich simplified things greatly. We never managed to make the arduino register newlines properly, but it wasn't really neccessary for the timer, so we moved on.
###Part 4
The commands were a fairly quick fix. Once we knew how to work the String libary, implementing a crude command parser was straightforward.
###Part 5
Moving right along to the timer. We didn't do any fancy formatting, just gave the arduino a 1000-millisecond ticking integer that it would display facilitated by the commands we programmed in part 4. It definitely worked, at least.
