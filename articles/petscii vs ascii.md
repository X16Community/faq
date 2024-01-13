#PETSCII and ASCII

Let's talk about PETSCII vs ASCII: 

Commodore, unlike virtually every other computer maker, uses a different order of letters in its character set.

On all computers, letters, numbers, symbols, and control codes ("Move that cursor left, please") are stored as numbers. Those numbers can translate to a printed character ("A"), a digit ("3"), or a command ("Move the paper up one row", or "move the print head to the start of the line").

Eventually, the computing and communicatins industry settled on the ASCII standard, as shown in this handy little chart: https://web.alfredstate.edu/faculty/weimandn/miscellaneous/ascii/ascii_index.html

ASCII is not the only encoding method used on computers: EBCDIC, Baudout, Fieldata, ITA-2, and a few others were experimented with until ASCII became standard on microcomputers. 

In ASCII, the letter "A" is stored as the number 65, "B" is 66, and so on. The lower case letters, "abc..." start at 97 and also go sequentially in ASCII. 

But the good folks at Commodore did something a little different. The 1977 Commodore PET did not have lower case letters. Instead, the engineers used that space for graphic symbols, which could be used for drawing boxes and charts. "A" is still 65, but there was no "a". Instead, pressing Shift+A prints the ♠ character, which actually lives at 193 in the PETSCII table. (65 + 128. Turns out the SHIFT key is basically the "add 128" key.)

This is called PETSCII. You can find a handy PETSCII chart here: https://www.c64-wiki.com/wiki/PETSCII

Well, as you might expect, users were all "HEY, IT MIGHT BE NICE IF WE COULD TYPE LOWER CASE LETTERS INSTEAD OF SHOUTING ALL THE TIME!" 

And Commodore said, "SURE, THAT SOUNDS LIKE A GOOD IDEA!" And a second version of the PET came out with a "Typewriter" keyboard and lower case text. 

Howver, instead of doing the obvious thing and altering the character set to add proper lower case letters, Commodore kept the behavior of the shift key (add 128) and moved the upper case letters to the space previously occupied by graphic symbols, making space for the lower case letters in that 65-90 zone. To make things more confusing, there were then two display modes: upper/lower text and upper case/graphics. The semantics of a specific character code didn't change, but its appearance did. 

So now, depending on the context, the letter "A" lives in up to 4 different places. (Because the codes used to actually display letters on the screen, aka "screen codes", are also moved around.)

So this leads us to the question: how do we fix it? The process is, surprisingly, not simple.

In upper-case/graphic mode (the default mode when a Commodore boots up):
A-Z on PC and Commodore are the same. 
a-z on PC become graphic symbols on Commodore. So don't use them. 

In upper/lower case mode: 
A-Z on PC should be mapped to 193-218. (Remember, "SHIFT" adds 128)
a-z on the PC get mapped to 65-90. 

And then the are "screen codes"... I'm just going to point you to Michael Steil's page on the topic, which gives more detail on the specifics: https://www.pagetable.com/?p=1404
