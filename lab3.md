# Lab Report 3
For this lab report I chose to research command-line options for `grep`.

I used ChatGPT as my source of information. For the prompt, I input "command line options for grep". Then, ChatGPT gnereated a list of commands and what they did.

## Ignoring case
Using the command-line option `-i` will ignore case when searching for what you input.
This is useful for when the user wants to easily search for a word without it being case-sensitive. This saves time by not having to type every single variation of capitalization. 

### First example
For example, when I type the command `grep -i "portland" ./technical/911report/chapter-1.txt`, the terminal outputs:
```

    For those heading to an airport, weather conditions could not have been better for a safe and pleasant journey. Among the travelers were Mohamed Atta and Abdul Aziz al Omari, who arrived at the airport in Portland, Maine.
    Boston: American 11 and United 175. Atta and Omari boarded a 6:00 A.M. flight from Portland to Boston's Logan International Airport.
    While Atta had been selected by CAPPS in Portland, three members of his hijacking team-Suqami, Wail al Shehri, and Waleed al Shehri-were selected in Boston. Their selection affected only the handling of their checked bags, not their screening at the checkpoint. All five men cleared the checkpoint and made their way to the gate for American 11. Atta, Omari, and Suqami took their seats in business class (seats 8D, 8G, and 10B, respectively). The Shehri brothers had adjacent seats in row 2 (Wail in 2A, Waleed in 2B), in the firstclass cabin. They boarded American 11 between 7:31 and 7:40. The aircraft pushed back from the gate at 7:40.

```
with every occurance of the word "portland" bolded and in red despite not capitalizing the "P" in Portland.

#### Without `-i`
For comparison, if I exclude `-i` and type in the command `grep "portland" ./technical/911report/chapter-1.txt`, the terminal will output nothing. Every time "Portland" appears in the text, the "P" is capitalized. Thus, no line will contain "portland" in all lowercase and the terminal will return nothing.

### Second Example
A second example is the command `grep -i "WHICH" ./technical/911report/chapter-10.txt`. This will output:
```

                situation with superiors in Washington. The President completed his statement, which
            President Bush also tasked the State Department, which on the following day delivered
                regarding a two-day visit to Afghanistan during which the Pakistani intelligence
                15 afternoon session, which dealt solely with Afghanistan.
                
```

Despite being in all caps, the terminal will still return every line that contains the word "which" no matter the case.

## Line Count
Using the command-line option `-c` will cause the terminal to return the amount of lines that contain the string given rather than print all the lines in their entirety.
This is useful for when there are too many lines that contain a string that it clogs up the terminal. I used it to find strings that when used for the `grep` command would output something easily readable. I don't want the terminal to show me hundreds of lines and make me count each line one at a time.

### First Example
An example is the command `grep -c "which" ./technical/911report/chapter-10.txt`, which outputs:
```
4
```

As you can see, the output is a number rather than lines of strings.

### Second Example
Another example is the command `grep -c -v "the" ./technical/911report/preface.txt`, which will output:
```
40
```

When searching for an extremely common word like the word "the", it helps to get a count of the lines instead of just seeing the contents of the lines.

## Inverted Matching
The command-line option `-v` will search for lines that do not contain the string given.
This is useful for when the user wants to exclude all lines that contain a word they don't want.

### First Example
One example would be typing in the command `grep -v "e" ./technical/biomed/1472-6793-2-5.txt`. This outputs:
```




        Background



          Purification
          ε
          280 and ε
          280 = 7.85 × 10 4cm -1M -1and ε
          551 = 4.8 × 10 4cm -1M -1) [ 5 ] .


          280 /ε
          Fig. 2.


          3).
          a pK
          pR at pH 6 or 8 (data not shown).



        Discussion

          Purification of pR
          H. salinarum.
          purifications is ~30%. Most of this loss, ~65%, occurs


          post-translationally.


          520 nm in
          that λ






          μs.


          structural configuration of 2 carboxylic acid groups and
          of E194 and E204 in bR.
          bR mutant E194Q [ 14 ] . In this mutant, Asp-85 was
          functional configuration.



        Conclusions
        post-translational modifications, including ~4000 daltons
        bR.



          E. coli strain UT5600 containing an


          Column purification
          of 1.5-2.0%. Fractions having an A
          280 /A
          280 /A






          Flash photolysis






```
This prints all lines that don't contain the letter "e", including the empty lines as well since they techinically don't contain the letter either.

### Second Example
A second example is typing in `grep -v "i" ./technical/911report/preface.txt`. The terminal will print:
```



            PREFACE
                27, 2002).
                learned.
                most complete account we can of the events of September 11, what happened and why.

```
For the sake of length, I chose single letters because each text file contained too many lines for an entire word to appear enough to exclude a large amount of lines. However, words can be used as well.

## Numbering
The command-line option `-n` will print the lines like usual, but also add which specific line numbers they come from.
This is useful for when the user wis searching for the specific line numbers that contain that string. This way, they can immediately go to that line in the file instead of manually searching themselves. This removes the frustration of constantly overlooking the word they are searching for.

### First Example
For the first example, typing in `grep -n "Congress" ./technical/911report/preface.txt` will output:
```

6:                the President of the United States, the United States Congress, and the American
14:            To answer these questions, the Congress and the President created the National
56:                Congress needs dramatic change as well to strengthen oversight and focus
68:                have been superb. We thank the Congress and the President. Executive branch agencies
75:                of several previous Commissions, and we thank the Congressional Joint Inquiry, whose

```

This command is helpful if I wanted to know which lines contained "Congress" so that I could go directly to the line that mentions it.

### Second Example
As a second example, the command `grep -n "which" ./technical/911report/chapter-10.txt` will output:
```
27:                situation with superiors in Washington. The President completed his statement, which
292:            President Bush also tasked the State Department, which on the following day delivered
377:                regarding a two-day visit to Afghanistan during which the Pakistani intelligence
464:                15 afternoon session, which dealt solely with Afghanistan.
```

If I was curious about how many times the word "which" appears, I could go to the individual lines.
