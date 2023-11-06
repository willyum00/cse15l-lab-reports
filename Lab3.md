# Lab 3 Report

## Part 1: Bugs

1. A failure inducing input for ArrayExamples
```java
@Test 
  public void testReversedInPlace(){
    int[] input = {1, 2, 3};
    ArrayExamples.reverseInPlace(input);
    assertArrayEquals(new int[]{3, 2, 1}, input);
  }
```

2. A non failure inducing input for ArrayExamples
```java
 @Test
  public void testReversedInPlaceEmpty(){
    int[] input = {};
    ArrayExamples.reverseInPlace(input);
    assertArrayEquals(new int[]{}, input);
  }
```

3. A screenshot of the symptom
   
   ![image](https://github.com/willyum00/cse15l-lab-reports/assets/81535097/2b7ed3e2-9982-40fc-854d-94da0ae629c3)

4. The bug

Original Code:
```java
   static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
Fixed Code:

```java
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length / 2 ; i += 1) {
      int j = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = j;
    }
  }

```

The bug in the original code was that there was no way for the "end" of the reversed version of the array to be filled. Halfway through the for loop, the array would repeat the first half of itself rather than reverse. I added a temporary variable to store the indexed value of the array and place it at the end, effectively swapping the front and end repeatedly. 


## Part 2: Researching Commands

I will be focusing on the grep command. 

The syntax for the grep command: 
```
grep [OPTION...] PATTERNS [FILE...]
```

So an example input would be 

```
grep "beagle" dogs.txt
```

The options I will be focusing on here are:

1. -i, ignore case
2. -v, invert match
3. -w
4. -c

I found these from codecamp's Grep Command in Linux – Usage, Options, and Syntax Examples article. 
Link: https://www.freecodecamp.org/news/grep-command-in-linux-usage-options-and-syntax-examples/#:~:text=Grep%20is%20a%20useful%20command,a%20powerful%20command%20to%20use.


I will give two examples for each of these options. 

1. -i (Note for these examples I was in the 911report directory) 

```
grep -i "old" chapter-3.txt
            FROM THE OLD TERRORISM TO THE NEW: THE FIRST WORLD TRADE CENTER
                "maximum feasible capacity" in counterterrorism by 2005. Field executives told
                told us they were not even aware that when they checked the names of incoming
            Inspector General of the Department ofTransportation told us, there were great
                security regulation as "decry, deny and delay" and told us that while "the air
            Cold War adversaries used very hierarchical, familiar, and predictable military
                geometric rate. At the same time, the end of the Cold War and the resultant cuts in
                Union during the Cold War are of limited use in identifying and tracking individual
            The Clandestine Service felt the impact of the post-Cold War peace dividend, with
            The CIA had been created to wage the Cold War. Its steady focus on one or two primary
            When the Cold War ended, those investments could not easily be reallocated to new
                rules that prevented adequate sharing of information. Another Cold War craft had
                cope with the new terrorism traced back to the early Cold War, when the Agency
                of the Cold War, it was not surprising that, with some notable exceptions, new hires
            Cuts in national security expenditures at the end of the Cold War led to budget cuts
                maintaining capability against older systems, such as high-frequency radios and
                ultra-high- and very-high-frequency (line of sight) systems that work like old-style
                told the Commission that his job was seen as a minor one within the department.
            The first was the passage by Congress in 1986 of the Goldwater-Nichols Act, which,
                presented to the president. The Goldwater-Nichols example is seen by some as having
                France plane and landed it at Entebbe in Uganda, holding 105 Israelis and other Jews
                the armed forces. It also contributed to the later Goldwater-Nichols reforms.
                killing two American soldiers. Intelligence clearly linked the bombing to Libya's
                States. The committees allow the CIA to some extent to withhold information in order
                of investigative journalists and watchdog organizations. Adjusting to the Post-Cold
                War Era The unexpected and rapid end of the Cold War in 1991 created trauma in the
                demand for imagery and continued capability against older systems, meant the need to
            With the Cold War over, and the intelligence community roiled by the Ames spy
                Aspin and later by former secretary of defense Harold Brown examined the
            Third, Congress did not reorganize itself after the end of the Cold War to address
                performed well. DCI Tenet told us: "We ran from threat to threat to threat. . . .
                border, not on terrorists. Justice Department officials told us that committees with
                questions, or what many members past and present told us was the proper conduct of
            .
            .
            .
            //about 50 more lines, so I cut them out for conciceness

```

What the above example is doing is it is finding any instance of the string "old" in the lines of file chapter-3.txt. It will return the line even if "old" is not a standalone word, but part of a word, such as "told" or "bold." Because I use the -i option, the capitalized OLD is returned as well. This could be useful for detecting patterns in a corpus, where we are not so worried about actual words as we are about strings of text. 

```
$ grep -i "evolves" chapter-3.txt
            COUNTERTERRORISM EVOLVES
```

The above example is finding any instance of the string "evolves" in the file chapter-3.txt. Unlike "old", there's only one instance of "evolves," and it is capitalized, but because we are using the -i option, the line is returned. This is of course useful if I want to find a particular word in a text file but can't remember if it is in the middle or start of a sentence, so ignoring case could solve that worry. 


2. -v invert match

```
grep -v "a" chapter-3.txt

    

            COUNTERTERRORISM EVOLVES
            FROM THE OLD TERRORISM TO THE NEW: THE FIRST WORLD TRADE CENTER
                BOMBING


                to kill 250,000 people.






                    documents.

            ADAPTATION-AND NONADAPTATION-IN THE LAW ENFORCEMENT COMMUNITY

                    priorities.

                worked closely with the U.S. Attorney for the Southern District of New York to
                received no credit.

                dubious.






                    priorities.


                desCOUNTERTERRORISM







                    collection.


                    prosecutors.





                    routinely.



                the FBI or CIA for counterterrorism use.



            Midlevel INS employees proposed comprehensive counterterrorism proCOUNTERTERRORISM



                    problem.


                Airport.

            Before 9/11, with the exception of one portion of the FBI, very little of the

             . . . AND IN THE FEDERAL AVIATION ADMINISTRATION






                    checkpoints.




                observed or vigorously enforced.



             . . . AND IN THE INTELLIGENCE COMMUNITY



                intelligence needs of their respective services.

                NSA's collection of foreign intelligence.

                terrorists.
                encrypted.
                more difficult.


                security functions." This structure built in tensions

                    officers.


                    Brief.

                knowledge.

                    high.


                    six.



                resources with which to work.



                entire U.S. intelligence effort. 3.5 . . . AND IN THE STATE DEPARTMENT AND THE


                governments presumed to be behind the terrorists. Moreover, since terrorist



                communities.
                rescue.

                    responses.

                    conflict.


                network.
             . . . AND IN THE WHITE HOUSE
                    interests."

                Poindexter.






                the country.



             . . . AND IN THE CONGRESS
                defense spending.
                effective oversight.
                to meet.

                problems.



                    projects.

                security. Committees with responsibility for the INS focused on the Southwest
                    oversight.


                exclusively devoted to counterterrorism, plus the briefings by its terrorist working
                second- or third-order priority within the committees of Congress responsible for

                oversight responsibilities.

            4 RESPONSES TO AL QAEDA'S INITIAL ASSAULTS
            BEFORE THE BOMBINGS IN KENYA AND TANZANIA



                Philippines in 1994-1995.







                "no policy."











                    proceed.




                July 23.


                did not survive."








            CRISIS: AUGUST 1998






                    shifting."


                    House.

                the President. The next month, Gingrich's office dismissed the cruise missile




                different countries.


                    1999.






            DIPLOMACY







                sources of his budget, or how he moved his money.





                difficult.













                    issue."







                    blessing.



                Pickering, "borne little fruit."

            COVERT ACTION

                QAEDA'S INITIAL ASSAULTS 127 Select Committee on Intelligence on September 2, Tenet







                request.





















                finished the job long before," RESPONSES TO AL QAEDA'S INITIAL ASSAULTS 133 but they
                    respect."

                    enough."







                U-2 flight never occurred.

            SEARCHING FOR FRESH OPTIONS
            "Boots on the Ground?"
                    missiles.











                    intelligence." But this course would still be risky,




                down so precisely.


                to strike the following morning.












                the lottery.






                to the decision.





```

In the above example, we are getting the invert match for the string "a". In other words, we are returning any line that DOES NOT have "a" in it. This could be useful for if we need to find outliers in a repetitive text file. 

For every following example, I am in the ./technical directory

```
$ grep -v "e" biomed/1468-6708-3-4.txt

  


        Introduction











          study.'



        1.)
        as (a) (24 (cr)+0)/54 = 44.4% and (b) (24 (cr)+24)/54 =
        48/54 = 88.9%.







          analysis.









        Conclusion




        imputation; MAR = missing at random; PI = partial
        imputation.




```

As with the previous example, we are returning every line that does not have the string "e" in it. Because "e" is such a common vowel, using it like this could help us analyze corpus and vowel usage statistics. 


3. -w option: find the exact matching word

```
$ grep -w "a" government/Media/Anthem_Payout.txt
dollars dropping, often unexpectedly, into the hands of a
But for some recipients, there is a downside to the checks from   
conversion to a publicly traded company.
TO avoid losing valuable benefits such as a Medicaid-paid spot    
in a nursing home, recipients may need to spend their money fast -
as early as the end of this month - but make sure they do it in a 
"You would think money out of the blue would be a good thing,"    
it is, and doesn't have a negative impact on low-income folks and 
operates a legal hotline for the elderly.
The basic advice is this: if you received a check or stock from   
call a legal-aid lawyer, benefits counselor or someone else who   
has a problem. It's legal service and it's free," said Amy Turner,
a staff attorney in Louisville with the Legal Aid Society, which
$2 billion in checks, plus shares of stock worth a bit more than
The distribution was a result of Anthem's conversion last year
from a mutual company, owned by its policyholders, to a publicly
people by surprise. And while it was generally a nice surprise, it
"I think there's a real danger that people will lose benefits
we are not in a position to provide advice to these people," she
She said the company believes the distribution has "been a
children to put it in a trust for them. The answer is no.
$10,000 for a car that is worth $2000," said Lee Richardson, a
The good news, for those who must spend up to $22,000 in a few
days, is that there is a fairly broad latitude in what you can
suggest such alternatives as buying a prepaid burial, paying
could include buying a car for medical transportation needs, making
spend the money," said Christopher Holly, a paralegal with Indian
```

in the above example, we are only returning lines that have the word "a" in it, so it will not return a line just because it has a word that includes the letter a in it. This is especially contrasted against the previous example of grep with "old" which would return lines with the words "told" or "bold." If we are interested in particular words, which we usually are, -a is a useful option. 


```
$ grep -w "Jaime" government/Media/Anthem_Payout.txt
said Jaime Odle Harmon, executive director of the Lexington-based
```

As in the previous example, this example shows how we can be more precise with finding words in a text with the -w option. 


4. -c: count the number of occurences of a pattern

```
$ grep -c "e"  government/Media/Anthem_Payout.txt
102
```

This option doesn't return any lines from the text, but returns an integer count of how many times the letter "e" occurs in the text file. This is especially helpful if we want to create a statistical analysis of a body of text's usage of certain vowels. 


```
$ grep -c -e "three days" -e "their stuff" government/Media/Fire_Victims_Sue.txt
2
```

Here, we are using the -c option to return the number of times the strings "three days" and "their stuff" appear in the same line. Which actually happens twice in the article. This is useful for if we want to capture redundancies in a body of text, or if we want to find unexpected patterns in our text. For this last example, I inputted the prompt "what are some useful applicaitons for the -c option for grep" into ChatGPT, and it showed an example of using -c with the -e option to flag specifying multiple patterns. This was its output:

```bash
1. Counting Multiple Patterns: You can count the occurrences of multiple patterns in a file by using grep with the -c option and the -e flag to specify multiple patterns.

grep -c -e "pattern1" -e "pattern2" file.txt

```
