# Lab Report 3
For this lab report I chose to research command-line options for `grep`.

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
