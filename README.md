# DIGITAL-HOURMETER
We are making a system to track the runtime of a host plant.  When the plant is running, it will 
send us a signal (running).  We will simply measure and store the time that the plant runs.  As a nice 
convenience for our end‐user, we’re including a reset button which will wipe out all of the time that has 
been accumulated allowing for a fresh start. 
## IO / ASSIGNED MEMORY
I:0/0 ‐ System running ,
N7:0 ‐ Seconds ,
N7:1 ‐ Minutes ,
N7:2 ‐ 100’s of hours, 
N7:3 ‐ 1000’s of hours, 
B3:0/0 ‐ Reset button .
### TEST CRITERIA
To start, run your program on Emulate.  N7:0‐N7:3 should all be sitting at zero.  These values should not 
be moving.  Not at all.  Not even a little bit. 
Next, force the system running input on (closed). Now we should see N7:0 accumulating seconds.  It 
should go from 0 to 59 over and over again.  Each time N7:0 counts a minute, N7:1 should go up by one.  
Eventually N7:1 should hit 59 and then go back to 0 itself.  When it does, N7:2 should go up by one.  Not 
that we’ll be leaving it running that long, but after N7:2 reaches 999, it should go back to 0 and N7:3 
should go up by one.  And on and on it goes.  To test that N7:2 and N7:3 work, you can manually change 
N7:1 and N7:2 setting each at its limit to make sure everything accumulates correctly. 
Third, force the system running input back off (open).  All of your accumulators (N7:0‐N7:3) should 
freeze right where they are. 
Fourth, force the system running input back on (closed) one last time.  The accumulators should keep 
counting from exactly where they left off. 
Finally, toggle B3:0/0 on and then back off.  N7:0‐N7:3 should all return to 0. 
