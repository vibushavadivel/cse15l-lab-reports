# Lab Report 3
---
#### Name: Vibusha Vadivel 
#### PID: A17825728 
#### Email: vvadivel@ucsd.edu
---

## Part 1
**Bug Chosen:** `reversed` method in `ArrayExamples`

**Failure Inducing Input:**
 ```
 @Test
  public void testReversedFailure() {
    int[] input1 = {8,7,6,5};
    assertArrayEquals(new int[]{5,6,7,8}, ArrayExamples.reversed(input1));
  }
```

**Non-failure Inducing Input:**
```
@Test
 public void testReversed() {
    int[] input1 = {};
    assertArrayEquals(new int[]{}, ArrayExamples.reversed(input1));
 }
```

**Symptoms**
![image](https://github.com/vibushavadivel/cse15l-lab-reports/assets/102670153/628c7ab5-e7b3-4f8c-9e4c-2eb01e9088e1)

**The Buggy Code Before:**
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
}
```
**The Buggy Code After (Fixed):**
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
}
```
**Description**: The bug was in the third line of the body of the method. Instead of assigning the value of the input array, the buggy code assigned the values of the new initialized array filled with 0 values to the old array (newArray). It then returned the original input array (arr), now containing the 0 values of newArray. Instead I switched the assignement so that the empty new initialized array, newArray, would be assigned the values of the input array in reverse order (arr.length - 1 - i). I also changed it so that the method returned newArray, so that the return value was actually updated with the values in reverse order.

## Part 2 - `grep`
### -v or --invert-match
**Example 1:**
```
$ grep -v "A Perk of Age: Free Legal Advice" ./technical/government/Media/A_Perk_of_Age.txt





By Kelly Greene
Free Legal advice is only a phone call away - and the hot lines
that provide it are expanding their services.
It's a little known perk available to anyone 60 or older: 21
states, Washington D.C., and Puerto Rico operate legal-assistance
hot lines for older adults and most take calls from younger
caregivers as well. Volunteers offer advice on legal questions,
provide self-help materials, and make referrals to legal aid
offices and pro bono or reduced-fee private lawyers. Even if you
live in a state without a hot line, local agencies on aging will
provide you with referrals to nearby lawyers. The hot lines and
referral services tackle estate planning, pension, and health
benefits, elder abuse and neglect, guardianship custodial issues
involving grandchildren, consumer protection and other elder-law
issues.
The U.S. administration on Aging coordinates this loosely knit
legal-services network. Anyone who meets the age requirement can
call the hot line, but hands-on legal counsel goes first to people
with the greatest financial or social needs. The federal Agency
recently awarded $2 million in grants to improve elder-law
services, with the largest part being used to bolster 12 hotlines
around the country, some of which are adding Web-based
questionnaires and outreach projects in rural areas and for older
people who don't speak English.
For a list of where the hotlines operate, along with their phone
numbers and hours, go to www.aoa.gov/legal/hotline.html, or call
the federal Eldercare Locator at 800-677-1116. If you live in a
state without a hot line, the locator can point you to local legal
assistance.
Another source of low-cost help also expanded this year: AARP's
Legal Services Network is now available in 46 states and expects to
reach all 50 by the end of March. You have to pay the group's dues
($10 a year) to use the services; after that you get 30 minutes of
legal counseling, either face-to-face or by phone, at no cost.
Lawyers discount their usual rate by 20% after that. Simple wills
cost $75 apiece. You can reach the service at 800-424-3410 or go to
www.aarp.org/LSN to find a lawyer nearby.



```

Explanation: The option -v for the grep command returns the contents of the file that do not match the given pattern, signified through "" quotation marks. In this example, "A Perk of Age: Free Legal Advice" is the given pattern and so the contents of the A_Perk_of_Age.txt file is returned without this line at the beginning. 

**Example 2:**
```
$ grep -v "war" technical
grep: technical: Is a directory
```
Explanation: The option -v for the grep command does not work on directories. It only works when a valid file path is provided.

### -i or --ignore-case
**Example 3:**
```
$ grep -i "War " ./technical/911report/chapter-2.txt
                declared war against God and his messenger, they called for the murder of any
                the Messenger and to communicate his message to all nations," and to serve as the rallying point and organizer of a new kind of war to
                of mankind." If the United States did not comply, it would be at war with the
                the overwhelmingly secular struggles for independence after World War I.
                progress. After gaining independence from Western powers following World War II, the
                President Anwar Sadat in 1981, the Egyptian government combined harsh repression of
                victory, triggering a brutal civil war that continues today. Opponents of today's
            Bin Ladin agreed to help Turabi in an ongoing war against African Christian
            BUILDING AN ORGANIZATION, DECLARING WAR ON THE UNITED STATES
                Gulf War of 1991. Moreover, Bin Ladin had in fact been sponsoring anti-Saddam
                the Afghan war through the Farouq mosque in Brooklyn. He had joined al Qaeda and
                enterprise for war against the United States.
            Yet Bin Ladin was in his weakest position since his early days in the war against the
                conveyed the same message-the duty of Muslims to carry out holy war against the
```
Explanation: The option -i ignores the case of the given pattern when matching the pattern with the lines of the given file. In this example, although "War " was provided as the string pattern, it outputted any line containing the substring "war " because, -i matched the contents of the file to the pattern "war " igorning the case.

**Example 4:**
```
$ grep -i "chapter" ./technical/911report
grep: ./technical/911report: Is a directory
```
Explanation: The option -i for the grep command does not work on directories. It only works when a valid file path is provided.

### -n or --line-number
**Example 5:**

```
$ grep -n "the " ./technical/government/Media/5_Legal_Groups.txt
5:5 Legal Groups at 1 Locale To Serve the February 3, 2002
11:services to the poor, ethnic minorities, seniors and people with
16:campaign by an alliance of the non-profit providers of free legal
18:from Utah lawyers and foundations, was the first joint fund-raising
19:campaign of legal services agencies in the country, and the
20:Community Legal Center is the first joint office project of public
22:The Legal Aid Society of Salt Lake, the Disability Law Center,
23:the Multi-Cultural Legal Center, the Senior Lawyer Volunteer
24:Project and Utah Legal Services will share the new facility, and
26:Community Legal Center hosted by staff members of the five
27:agencies. All of the agencies can share the same reception area and
28:client waiting room. The building is close in, across the street
29:from West High and two blocks from the Gateway. It has its own
32:building and not paying rent times five will save the non-profit
34:Christenson, pointed out that the shared facility will also be
37:town trying to find the right agency.
38:After the tour, we found Jaye Olafson at the cookies and
39:brownies reception on the first floor. Jaye and her husband, Erik,
40:own Tomax Technologies and were the sellers of the building. Jaye
41:explained how much of the renovation had been merely uncovering
44:old paint. She loves the building, and they only moved out because
45:the business had outgrown the space. So they renovated the old
47:with the new owners. The building had been like home, she
49:noted on the donor list that the couple, through Olafson Group, had
50:become one of the major supporters of the project.
51:Stewart Ralphs, the executive director of the Legal Aid Society,
52:explained that the Community Legal Center Campaign still has a long
53:ways to go, with a bit more than half of the $4 million projected
56:in touch with us later on the subject.
```
Explanation: The option -n of the grep command adds the line number of each line within the input file that matches the passed in pattern (signified in ""). In this example, "the " was the pattern passed in and so each line containing the was prefixed with its line number within the 5_Legal_Groups.txt file. 

**Example 6:**
```
$ grep -n "1468" ./technical/biomed
grep: ./technical/biomed: Is a directory
```
Explanation: The option -n for the grep command does not work on directories. It only works when a valid file path is provided.

### -o, --only-matching
```
$ grep -o "JSTOR" ./technical/plos/journal.pbio.0020010.txt
JSTOR
JSTOR
JSTOR
JSTOR
JSTOR
JSTOR
JSTOR
JSTOR
JSTOR
JSTOR
JSTOR
JSTOR
JSTOR
JSTOR
JSTOR
JSTOR
JSTOR
JSTOR
JSTOR
JSTOR
JSTOR
JSTOR
JSTOR
```
Explanation: The option -o of the grep command, returns only the part of the line in the input file that matches the given pattern. In this command "JSTOR" was the input, hence all the lines contatining "JSTOR" are outputted with only the part of the line that matches the inputted pattern.

**Example 8:**
```
$ grep -o "journal" ./technical/plos
grep: ./technical/plos: Is a directory
```
Explanation: The option -o for the grep command does not work on directories. It only works when a valid file path is provided.

### Sources: 
- https://man7.org/linux/man-pages/man1/grep.1.html
- https://chat.openai.com/ (ChatGPT)
