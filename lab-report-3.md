## **Lab Report 3**

### The Grep Command

#### Basics
The `grep` command stands for "**g**lobal search for **r**egular **e**xpression and **p**rint out". It searches a file for a particular pattern and displays all the lines that contain the pattern. The following is the syntax of the command:

`grep [options] pattern [files]`

One example of using grep command without any options is the following:
```
$ grep "command center" technical/911report/chapter-1.txt
  At 10:02 that morning, an assistant to the mission crew commander at NORAD's Northeast Air Defense Sector in Rome, New York, was working with his
colleagues on the floor of the command center. In a brief moment of reflection, he was recorded remarking that "This is a new type of war.
```
The grep command searches the lines of `chapter-1.txt` file in the `911report` directory for the phrase "command center" and displays the lines with that pattern. In this case, there is one line in the text file that has this pattern.


#### Command-Line Options

Online, find 4 interesting command-line options or alternate ways to use the command you chose. For example, we saw the -name option for find in class. For each of those options, give 2 examples of using it on files and directories from ./technical. Show each example as a code block that shows the command and its output, and write a sentence or two about what it’s doing and why it’s useful.

The `grep` command has various command-line options, but here are four important ones. To show how these options function, we will use files and directories from `./technical`.

1. -c option displays only a count of the lines that match a pattern

**Example 1** 
```
$ grep -c "command center" technical/911report/chapter-1.txt
1
```
As we seen in the beginning, there is only one line in the chapter-1.txt file that matches the pattern "command center" exctly. Therefore the grep command with the -c option prints 1. 

**Example 2**
```
$ grep -c "BMI" technical/biomed/1468-6708-3-1.txt* 
32
```
There are 32 lines in 1468-6708-3-1.txt* file that matches the pattern "BMI". Therefore grep command with the -c option prints 32.

2. -i option ignores case sensitivity for matching.

**Example 1**
 ```
$ grep -i "command center" technical/911report/chapter-1.txt > 911_results2.txt
 United 175 was hijacked between 8:42 and 8:46, and awareness of that hijacking began to spread after 8:51. American 77 was hijacked between 8:51 and 8:54. By 9:00, FAA and airline officials began to comprehend that attackers were going after multiple aircraft. American Airlines' nationwide ground stop between 9:05 and 9:10 was followed by a United Airlines ground stop. FAA controllers at Boston Center, which had tracked the first two hijackings, requested at 9:07 that Herndon Command Center "get messages to airborne aircraft to increase security for the cockpit." There is no evidence that Herndon took such action. Boston Center immediately began speculating about other aircraft that might be in danger, leading them to worry about a transcontinental flight-Delta 1989-that in fact was not hijacked. At 9:19, the FAA's New England regional office called Herndon and asked that Cleveland Center advise Delta 1989 to use extra cockpit security.
    Many controllers work at the FAA's 22 Air Route Traffic Control Centers. They are grouped under regional offices and coordinate closely with the national Air Traffic Control System Command Center, located in Herndon, Virginia, which oversees daily traffic flow within the entire airspace system. FAA headquarters is ultimately responsible for the management of the National Airspace System. The Operations Center located at FAA headquarters receives notifications of incidents, including accidents and hijackings.
    FAA Control Centers often receive information and make operational decisions independently of one another. On 9/11, the four hijacked aircraft were monitored mainly by the centers in Boston, New York, Cleveland, and Indianapolis. Each center thus had part of the knowledge of what was going on across the system. What Boston knew was not necessarily known by centers in New York, Cleveland, or Indianapolis, or for that matter by the Command Center in Herndon or by FAA headquarters in Washington.
    If a hijack was confirmed, procedures called for the hijack coordinator on duty to contact the Pentagon's National Military Command Center (NMCC) and to ask for a military escort aircraft to follow the flight, report anything unusual, and aid search and rescue in the event of an emergency. The NMCC would then seek approval from the Office of the Secretary of Defense to provide military assistance. If approval was given, the orders would be transmitted down NORAD's chain of command.
    Between 8:25 and 8:32, in accordance with the FAA protocol, Boston Center managers started notifying their chain of command that American 11 had been hijacked. At 8:28, Boston Center called the Command Center in Herndon to advise that it believed American 11 had been hijacked and was heading toward New York Center's airspace.
    By this time, American 11 had taken a dramatic turn to the south. At 8:32, the Command Center passed word of a possible hijacking to the Operations Center at FAA headquarters. The duty officer replied that security personnel at headquarters had just begun discussing the apparent hijack on a conference call with the New England regional office. FAA headquarters began to follow the hijack protocol but did not contact the NMCC to request a fighter escort.
    The Herndon Command Center immediately established a teleconference between Boston, New York, and Cleveland Centers so that Boston Center could help the others understand what was happening.
    At 8:48, while the controller was still trying to locate American 11, a New York Center manager provided the following report on a Command Center teleconference about American 11:
    Between 9:01 and 9:02, a manager from New York Center told the Command Center in Herndon:
    The "other aircraft" referred to by New York Center was United 175. Evidence indicates that this conversation was the only notice received by either FAA headquarters or the Herndon Command Center prior to the second crash that there had been a second hijacking.
    While the Command Center was told about this "other aircraft" at 9:01, New York Center contacted New York terminal approach control and asked for help in locating United 175.
    Boston Center immediately advised the New England Region that it was going to stop all departures at airports under its control. At 9:05, Boston Center confirmed for both the FAA Command Center and the New England Region that the hijackers aboard American 11 said "we have planes." At the same time, New York Center declared "ATC zero"-meaning that aircraft were not permitted to depart from, arrive at, or travel through New York Center's airspace until further notice.
    Within minutes of the second impact, Boston Center instructed its controllers to inform all aircraft in its airspace of the events in New York and to advise aircraft to heighten cockpit security. Boston Center asked the Herndon Command Center to issue a similar cockpit security alert nationwide. We have found no evidence to suggest that the Command Center acted on this request or issued any type of cockpit security alert.
    By 9:20, Indianapolis Center learned that there were other hijacked aircraft, and began to doubt its initial assumption that American 77 had crashed. A discussion of this concern between the manager at Indianapolis and the Command Center in Herndon prompted it to notify some FAA field facilities that American 77 was lost. By 9:21, the Command Center, some FAA field facilities, and American Airlines had started to search for American 77. They feared it had been hijacked. At 9:25, the Command Center advised FAA headquarters of the situation.
    In sum, Indianapolis Center never saw Flight 77 turn around. By the time it reappeared in primary radar coverage, controllers had either stopped looking for the aircraft because they thought it had crashed or were looking toward the west. Although the Command Center learned Flight 77 was missing, neither it nor FAA headquarters issued an all points bulletin to surrounding centers to search for primary radar targets. American 77 traveled undetected for 36 minutes on a course heading due east for Washington, D.C.
    By 9:25, FAA's Herndon Command Center and FAA headquarters knew two aircraft had crashed into the World Trade Center. They knew American 77 was lost. At least some FAA officials in Boston Center and the New England Region knew that a hijacker on board American 11 had said "we have some planes." Concerns over the safety of other aircraft began to mount. A manager at the Herndon Command Center asked FAA headquarters if they wanted to order a "nationwide ground stop." While this was being discussed by executives at FAA headquarters, the Command Center ordered one at 9:25.
    The Command Center kept looking for American 77. At 9:21, it advised the Dulles terminal control facility, and Dulles urged its controllers to look for primary targets. At 9:32, they found one. Several of the Dulles controllers "observed a primary radar target tracking eastbound at a high rate of speed" and notified Reagan National Airport. FAA personnel at both Reagan National and Dulles airports notified the Secret Service. The aircraft's identity or type was unknown.
    Right after the Pentagon was hit, NEADS learned of another possible hijacked aircraft. It was an aircraft that in fact had not been hijacked at all. After the second World Trade Center crash, Boston Center managers recognized that both aircraft were transcontinental 767 jetliners that had departed Logan Airport. Remembering the "we have some planes" remark, Boston Center guessed that Delta 1989 might also be hijacked. Boston Center called NEADS at 9:41 and identified Delta 1989, a 767 jet that had left Logan Airport for Las Vegas, as a possible hijack. NEADS warned the FAA's Cleveland Center to watch Delta 1989. The Command Center and FAA headquarters watched it too. During the course of the morning, there were multiple erroneous reports of hijacked aircraft. The report of American 11 heading south was the first; Delta 1989 was the second.
    FAA headquarters had by this time established an open line of communication with the Command Center at Herndon and instructed it to poll all its centers about suspect aircraft. The Command Center executed the request and, a minute later, Cleveland Center reported that "United 93 may have a bomb on board." At 9:34, the Command Center relayed the information concerning United 93 to FAA headquarters. At approximately 9:36, Cleveland advised the Command Center that it was still tracking United 93 and specifically inquired whether someone had requested the military to launch fighter aircraft to intercept the aircraft. Cleveland even told the Command Center it was prepared to contact a nearby military base to make the request. The Command Center told Cleveland that FAA personnel well above them in the chain of command had to make the decision to seek military assistance and were working on the issue.
    From 9:34 to 10:08, a Command Center facility manager provided frequent updates to Acting Deputy Administrator Monte Belger and other executives at FAA headquarters as United 93 headed toward Washington, D.C. At 9:41, Cleveland Center lost United 93's transponder signal. The controller located it on primary radar, matched its position with visual sightings from other aircraft, and tracked the flight as it turned east, then south.
    At 9:42, the Command Center learned from news reports that a plane had struck the Pentagon. The Command Center's national operations manager, Ben Sliney, ordered all FAA facilities to instruct all aircraft to land at the nearest airport. This was an unprecedented order. The air traffic control system handled it with great skill, as about 4,500 commercial and general aviation aircraft soon landed without incident.
    At 9:46 the Command Center updated FAA headquarters that United 93 was now "twenty-nine minutes out of Washington, D.C." At 9:49, 13 minutes after Cleveland Center had asked about getting military help, the Command Center suggested that someone at headquarters should decide whether to request military assistance: FAA Headquarters: They're pulling Jeff away to go talk about United 93.
    Command Center: Uh, do we want to think, uh, about scrambling aircraft?
    Command Center: Uh, that's a decision somebody's gonna have to make probably in the next ten minutes.
    At 9:53, FAA headquarters informed the Command Center that the deputy director for air traffic services was talking to Monte Belger about scrambling aircraft. Then the Command Center informed headquarters that controllers had lost track of United 93 over the Pittsburgh area. Within seconds, the Command Center received a visual report from another aircraft, and informed headquarters that the aircraft was 20 miles northwest of Johnstown. United 93 was spotted by another aircraft, and, at 10:01, the Command Center advised FAA headquarters that one of the aircraft had seen United 93 "waving his wings." The aircraft had witnessed the hijackers' efforts to defeat the passengers' counterattack.
    Five minutes later, the Command Center forwarded this update to headquarters: Command Center: O.K. Uh, there is now on that United 93.
    Command Center: There is a report of black smoke in the last position I gave you, fifteen miles south of Johnstown.
    Command Center: Uh, they're speculating it's from the aircraft. FAA Headquarters: Okay.
    Command Center: Uh, who, it hit the ground. That's what they're speculating, that's speculation only.
    The aircraft that spotted the "black smoke" was the same unarmed Air National Guard cargo plane that had seen American 77 crash into the Pentagon 27 minutes earlier. It had resumed its flight to Minnesota and saw the smoke from the crash of United 93, less than two minutes after the plane went down. At 10:17, the Command Center advised headquarters of its conclusion that United 93 had indeed crashed.
    We do not believe that the true picture of that morning reflects discredit on the operational personnel at NEADS or FAA facilities. NEADS commanders and officers actively sought out information, and made the best judgments they could on the basis of what they knew. Individual FAA controllers, facility managers, and Command Center managers thought outside the box in recommending a nationwide alert, in ground-stopping local traffic, and, ultimately, in deciding to land all aircraft and executing that unprecedented order flawlessly.
    Inside the National Military Command Center, the deputy director of operations and his assistant began notifying senior Pentagon officials of the incident. At about 9:00, the senior NMCC operations officer reached out to the FAA operations center for information. Although the NMCC was advised of the hijacking of American 11, the scrambling of jets was not discussed.
The Pentagon Teleconferences. Inside the National Military Command Center, the deputy director for operations immediately thought the second strike was a terrorist attack. The job of the NMCC in such an emergency is to gather the relevant parties and establish the chain of command between the National Command Authority-the president and the secretary of defense- and those who need to carry out their orders.
    At 10:02 that morning, an assistant to the mission crew commander at NORAD's Northeast Air Defense Sector in Rome, New York, was working with his colleagues on the floor of the command center. In a brief moment of reflection, he was recorded remarking that "This is a new type of war."
 ```
At first, the grep command only found one line in chapter-1.txt that matched the pattern "command center", but when the -i flag option was used, the grep command found 34 lines. This is because the command ignored case sensitvity and thus displayed all lines consisting of the pattern in some form (lowercase and uppercase).

**Example 2**

3. -v option displays all the lines that do not matches the pattern
**Example 1** 
**Example 2**

4. -l option displays list of file names only
**Example 1** 
**Example 2**

#### Cited Sources
https://www.geeksforgeeks.org/grep-command-in-unixlinux/
https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix


