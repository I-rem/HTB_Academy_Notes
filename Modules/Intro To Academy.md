# Intro To Academy
This module is a short and friendly introduction to the platform. Other than being the first step for practical side of things I also found this module to be a good start for getting your **mindset** right.

## Some good advice
- Don't be intimitaded
- Take it one step at a time 
- Constantly test your knowledge

Remember:  _“Great things are not done by impulse, but by a series of small things brought together.”_ **Vincent Van Gogh**

- Join the community
	- [Hack The Box Discord server](https://discord.com/invite/hackthebox)
	-  [Hack The Box Forum](https://forum.hackthebox.com/)
	 - [Hack The Box Sub-reddit](https://www.reddit.com/r/hackthebox/)
## Questions
### Section: Modules
 **Q:** This module is a tier 0 "free" module. What is the total cubes that will be rewarded back to you by completing it?

 **A:** 10
 
 **Explanation:** Each module costs a specific `amount of cubes` to unlock, and will always `return 20% of those cubes` back upon 100% completion of the module. `Tier 0` modules are considered `free modules`, as they cost 10 cubes and reward back 10 cubes
### Section: Sections
**Q:**  Start your workstation, then use the integrated terminal to find the Linux OS flavor by running the following command: cat /etc/issue

**A:** Parrot

**Explanation:**  We are provided with the full command, so this should be very straightforward 

We start the instance and we are greeted with this desktop

![image](https://github.com/user-attachments/assets/69e293bd-f5e2-480b-be7c-0b439367a29f)

We then open the terminal and type in the command `cat /etc/issue`

`cat` is a command that is used to concatenate and display the file contents

`/etc` is the directory where various system files are stored in Linux

`/etc/issue` is a text file which contains a message or system identification to be printed before the login prompt.

All of this and more will be explained in the other modules (see: [[Linux Fundamentals]]) so no worries if this is your first experience with a command-line-interface.

Here is the output of our command:

![image](https://github.com/user-attachments/assets/6923dd1c-9958-41c5-bdca-f209bb9737d4)

Linux comes in many distros and HTB Academy chose to go for ParrotOS. But why?

_Parrot was designed to be a very comfortable environment for security experts and researchers. It includes a full portable arsenal for IT security and digital forensics operations._

See more at [parrotsec.org](https://parrotsec.org/docs/introduction/what-is-parrot/#:~:text=Parrot%20Security%20(ParrotOS%2C%20Parrot),security%20and%20digital%20forensics%20operations.)

There will be a more detailed explanation of various tools and what to look for in a home-setup in the [[Setting Up]] module.

Also most of the time there will be many different ways to get the same result.  Read writeups from different people to see various solutions.

Alternative solution: `$ cat /etc/os-release` 

![image](https://github.com/user-attachments/assets/b1bd7b64-7079-4a86-a7f3-38403fa1df8b)

## Section Exercises
**Q:**  Start the above target, copy the shown IP:PORT by clicking on them, and then paste them in your browser. What's the proof shown in the page?

**A:** t4rg3ts

**Explanation:** This exercion just wants to teach us how to spawn the target system.  

![image](https://github.com/user-attachments/assets/56f4738d-68ef-4d47-ae66-f7771a4f670a)

Spawn the target, start the instance, open the browser and paste the target address. 

Done!

![image](https://github.com/user-attachments/assets/04f5daf3-30dc-4e82-8a04-2e4f2a20fcf7)
