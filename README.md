# CSE-381-Systems-2-Homework-2

Download Here: [CSE-381: Systems 2 Homework #2](https://codingherolab.com/product/cse-381-systems-2-homework-2/)

For Custom/Original Work email codingprolab@gmail.com/whatsapp +1(541)423-7793

Develop program to print group membership
Objective
The objective of this program is to print login-IDs of the users belonging to a given set of gids
(group IDs) specified as command-line arguments. The necessary data is read from 2 given text
files.
Background
In Linux, users are internally represented using a unique number called user ID or uid.
Moreover, a set of users can be logically organized into a group. Such groups are represented by
a group ID or gid. Typically, these numbers are seldom used and instead a name is associated
with these numbers and the names are often used. This program will serve as an excellent tool to
quickly identify membership in a given group.
Data file formats
Prior to solving any problem is important to study the supplied data. So, ensure you view the
data files (yes, of course you can do this in NetBeans). The supplied data files used are nearly
in the same format as they are in a real Linux OS as described below. Needless to add, you will
need to scp these files to your NetBeans project in order to read/use them.
• User data (passwd): The supplied passwd file contains user information in the
following colon (:) delimited format:
loginID:passkey:uid:…
For example, the following line from passwd “raodm:xyz:1000:…” contains the
login ID raodm as the first entry, xyz is some passkey (not used) followed by the uid
(int). Rest of the information on each line is not used in this project.
• Group information (groups): The supplied groups file contains group information
in the following colon (:) delimited format:
groupID:passkey:gid:members…
For example, the following line from groups “staff:x123:3:1002,1000”
contains the group ID staff as the first entry, x123 is some passkey (not used)
followed by the gid (int), followed by a comma separated list of uids. This results in
group corresponding to output “3 = staff: lewisjp3(1002)
raodm(1000)”, where the uid for each loginID is shown in parentheses. The
loginID for an uid is in the passwd file, described just above.

Sample outputs
One you have completed your program you can test its operation using the command shows
below and compare your output to the output shown below. See https://youtu.be/R8BgAGjY14M
for a video demonstration of setting command-line arguments in NetBeans. Note that group IDs
are specified as command-line arguments.
Base case #1 [Must pass to earn any points]:
Simple test with exactly 1 valid group ID as a command-line argument

$ ./raodm_hw2 0
0 = root: root(0)

Base case #2 [Must pass to earn any points]:
Simple test with exactly 1 valid group ID as a command-line argument
$ ./raodm_hw2 1
1 = bin:
Test case #3 [Additional feature]:
Test with an invalid group id
$ ./raodm_hw2 100
100 = Group not found.
Test case #4 [Additional Feature]:
Test with many valid/invalid group IDs supplied as command-line arguments
$ ./raodm_hw2 0 1 2 6 100 6 2
0 = root: root(0)
1 = bin:
2 = faculty: raodm(1000) campbest(1001) kiperjd(1003) raychov(1004)
bachmaer(2000) inclezd(1500) davisk4(2001) femianjc(2002) crossv(2010)
castroa(2011) ahmede(2012)
6 = theory: davisk4(2001) inclezd(1500) raychov(1004) femianjc(2002)
100 = Group not found.
6 = theory: davisk4(2001) inclezd(1500) raychov(1004) femianjc(2002)
2 = faculty: raodm(1000) campbest(1001) kiperjd(1003) raychov(1004)
bachmaer(2000) inclezd(1500) davisk4(2001) femianjc(2002) crossv(2010)

Notes/Tips:
• Use std::ifstream to read data from the text files.
• Using command-line arguments in your C++ program is covered in

• Use std::istringstream to process each line read using std::getline
method. See example in lecture slides on processing Comma Separated Values (in Part 4
of C++ topics). Here is convenience link to that spot in the video:

• Use an unordered_map to store uidÛloginID information to ease look-up from
processing group membership.

• It would be easier to compute and store the line of output to print for each gid in another unordered_map. • Here are the #includes in the reference solution for your convenient reference: #include #include #include #include #include #include Submit to Canvas This homework assignment must be turned-in electronically via Canvas via the CODE Plugin. Ensure your program compiles without any warnings or style violations and operates correctly, at least for the base case. Once you have tested your implementation, upload just one C++ source file via the CODE plugin.

 
