# `RHM`: Robot Hacking Manual

[<ins>Download in PDF `RHM v0.4`<ins>](https://github.com/vmayoral/robot_hacking_manual/releases/download/0.4/RHM.pdf) ┃ <span style="background-color: #FFFF00">[Read online](https://rhm.cybersecurityrobotics.net/)</span>

The *Robot Hacking Manual* (`RHM`) is an introductory series about cybersecurity for robots, with an attempt to provide comprehensive case studies and step-by-step tutorials with the intent to raise awareness in the field and highlight the importance of taking a *security-first*[^0] approach. The material available here is also a personal learning attempt and it's disconnected from any particular organization. Content is provided as is and **by no means I encourage or promote the unauthorized tampering of robotic systems or related technologies**.

- [**Disclaimer**](DISCLAIMER.md)
- [**History**](MOTIVATION.md#history)
- [**Motivation**](MOTIVATION.md#motivation)
- [**A containerized approach**](MOTIVATION.md#a-containerized-approach)
- [**Contribute back**](CONTRIBUTE.md)
- [**Introduction**](0_introduction/README.md)
  - [About robot cybersecurity](0_introduction/README.md#about-robot-cybersecurity)
- <ins>**Case studies**</ins>
  - [Universal Robots' UR3](1_case_studies/0_cobot/) (hacking a collaborative robot arm)
  - [Mobile Industrial Robots' MiR100](1_case_studies/1_amr/) (hacking an industrial mobile robot)
  - [Robot Operating System](1_case_studies/3_turtlebot3/) (hacking ROS 1)
  - [Robot Operating System 2](1_case_studies/2_ros2/) (hacking ROS 2)
  - [TurtleBot 3](1_case_studies/4_ros/) (hacking TurtleBot 3)
  - [PX4 autopilot](1_case_studies/5_px4/)
- [**Writeups**]()
  - <ins>Reconaissance</ins>
    - Footprinting
      - [Tutorial 1: Footprinting ROS systems](2_writeups/1_reconnaissance/robot_footprinting/tutorial1/)
      - [Tutorial 2: Footprinting Secure ROS systems](2_writeups/1_reconnaissance/robot_footprinting/tutorial2/)
      - [Tutorial 3: Footprinting ROS 2 and DDS systems](2_writeups/1_reconnaissance/robot_footprinting/tutorial3/)
  - <ins>Vulnerability research</ins>
    - Static analysis
      - [Tutorial 5: Static analysis of PyRobot](2_writeups/2_robot_vulnerabilities/tutorial5/)
    - Dynamic analysis
      - [Tutorial 1: Robot sanitizers in ROS 2 Dashing](2_writeups/2_robot_vulnerabilities/tutorial1/)
      - [Tutorial 2: Robot sanitizers in MoveIt 2](2_writeups/2_robot_vulnerabilities/tutorial2/)
      - [Tutorial 3: Debugging output of robot sanitizers with GDB, hunting and fixing bugs](2_writeups/2_robot_vulnerabilities/tutorial3/)
      - ~~Tutorial 4: Robot sanitizers with Gazebo~~
      - [Tutorial 5: Static analysis of PyRobot](2_writeups/2_robot_vulnerabilities/tutorial5/)
      - [Tutorial 6: Looking for vulnerabilities in ROS 2](2_writeups/2_robot_vulnerabilities/tutorial6/)
      - [Tutorial 7: Analyzing Turtlebot 3](2_writeups/2_robot_vulnerabilities/tutorial7/)
      - [Tutorial 8: SROS and SROS 2, exploring](2_writeups/2_robot_vulnerabilities/tutorial8/)
      - [Tutorial 9: Looking at DDS middleware flaws](2_writeups/2_robot_vulnerabilities/tutorial8/)
  - <ins>Exploitation</ins>
    - General
      - [Tutorial 1: Buffer overflows](2_writeups/3_robot_exploitation/tutorial1/)
      - [Tutorial 2: Building shellcode](2_writeups/3_robot_exploitation/tutorial2/)
      - [Tutorial 3: Exploiting](2_writeups/3_robot_exploitation/tutorial3/)
      - [Tutorial 4: Return to `libc`](2_writeups/3_robot_exploitation/tutorial4/)
      - [Tutorial 5: Return-Oriented Programming (ROP)](2_writeups/3_robot_exploitation/tutorial5/)
      - [Tutorial 6: Remote shell](2_writeups/3_robot_exploitation/tutorial6/)
      - [Tutorial 7: pwntools - CTF toolkit](2_writeups/3_robot_exploitation/tutorial7/)
      - [Tutorial 8: Linux Binary Protections](https://github.com/nnamon/linux-exploitation-course/blob/master/lessons/5_protections/lessonplan.md) (external)
      - [Tutorial 9: Building a pwnbox](2_writeups/3_robot_exploitation/tutorial9/)
      - [Tutorial 10: Bypassing NX with Return Oriented Programming](2_writeups/3_robot_exploitation/tutorial10/) (**WIP, unfinished**)
    - Robotics-specific
      - [Tutorial 11: Unauthenticated registration/unregistration with ROS Master API](2_writeups/3_robot_exploitation/tutorial11/)
      - [Tutorial 12: Unauthenticated updates in publisher list for specified topic](2_writeups/3_robot_exploitation/tutorial12)
      - [Tutorial 13: Sockets left open and in CLOSE_WAIT state in ROS](2_writeups/3_robot_exploitation/tutorial13)
  - <ins>Forensics</ins>
    - [Tutorial 1: Basic robot forensics, an unauthenticated unregistration in ROS](2_writeups/4_other/robot_forensics/tutorial1/)
    - [Tutorial 2: Locating ROS logs in memory](2_writeups/4_other/robot_forensics/tutorial2/) (**failed**)
    - [Tutorial 3: Capturing memory in Linux-based robots](2_writeups/4_other/robot_forensics/tutorial3/)
    - [Tutorial 4: Basic robot forensics 2, unauthenticated updates in publisher list for specified topic](2_writeups/4_other/robot_forensics/tutorial4/) (**unfinished**)
  - <ins>Hardening</ins>
    - [Tutorial 1: A study of container technologies](2_writeups/4_other/hardening/tutorial1/README.md)
- **Talks**:
  - <ins>2016</ins>
    - [Securing ROS over the wire, in the graph, and through the kernel](https://vimeo.com/187705073), ROSCon 2016
  - <ins>2017</ins>
    - [Hacking Robots Before Skynet](https://www.youtube.com/watch?v=LK43J-p1H3o), Ekoparty Security Conference 2017
    - [An Experimental Security Analysis of an Industrial Robot Controller](https://www.youtube.com/watch?v=tGcNefddfZM), IEEE Symposium on Security and Privacy 2017
    - [SROS: Current Progress and Developments](https://vimeo.com/236172830), ROSCon 2017
    - [Breaking the Laws of Robotics: Attacking Industrial Robots](https://www.youtube.com/watch?v=RKLUWnzIaP4), Black Hat USA 2017
  - <ins>2018</ins>
    - [Introducing the Robot Security Framework](https://www.youtube.com/watch?v=Gv4O2Xw8MUk&list=PLf4Fnww4KiFdjCAfs04ynv40xbpqFPibm&index=11) (spanish), Navaja Negra Conference 2018
    - [Arm DDS Security library: Adding secure security to ROS2](https://vimeo.com/292703899), ROSCon 2018
    - [Leveraging DDS Security in ROS 2](https://vimeo.com/292703074), ROSCon 2018
  - <ins>2019</ins>
    - [Defensive and offensive robot security](https://www.youtube.com/watch?v=aEQgga_MnO8&list=PLf4Fnww4KiFdjCAfs04ynv40xbpqFPibm&index=9), ROS-Industrial Conference 2019
    - [Black Block Recorder: Immutable Black Box Logging via rosbag2 and DLTs](https://vimeo.com/378682905), ROSCon 2019
    - *Lessons learned on real-time and security* ([slides](https://aliasrobotics.com/files/realtimesecurity.pdf)), ROS 2 Real-Time Workshop, ROSCon 2019
  - <ins>2020</ins>
    - [Current security threat landscape in robotics](https://www.youtube.com/watch?v=5pWqROTERgU&list=PLf4Fnww4KiFdjCAfs04ynv40xbpqFPibm&index=10), European Robotics Forum (ERF) 2020
    - [Security in ROS & ROS 2 robot setups](https://www.youtube.com/watch?v=n7BvyUgKP-M&list=PLf4Fnww4KiFdjCAfs04ynv40xbpqFPibm&index=11), European Robotics Forum (ERF) 2020
    - [Akerbeltz, industrial robot ransomware](https://www.youtube.com/watch?v=5dYmpKH_3EM), International Workshop on Engineering Resilient Robot Software Systems, International Conference on Robotic Computing (IRC 2020).
    - [Zero Trust Architecture in Robotics](https://www.youtube.com/watch?v=jfPw8gH1i2I), Workshop on Security and Privacy in Robotics, ICRA 2020
    - [The cybersecurity status of PX4](https://www.youtube.com/watch?v=phHYfAqjOuQ&list=PLf4Fnww4KiFdjCAfs04ynv40xbpqFPibm&index=13), PX4 Developer Summit Virtual 2020
    - [Detecting Insecure Code Patterns in Industrial Robot Programs](https://dl.acm.org/doi/10.1145/3320269.3384735#sec-supp), Proceedings of the 15th ACM Asia Conference on Computer and Communications Security 2020
    - [Protecting robot endpoints against cyber-threats](https://www.youtube.com/watch?v=jo_L9Ra8UqU&list=PLf4Fnww4KiFdjCAfs04ynv40xbpqFPibm&index=14), ROS-Industrial Conference 2020
    - [Robots and Privacy](https://www.youtube.com/watch?v=Yu3lgESCB8M), Shmoocon 2020
  - <ins>2021</ins>
    - [Uncovering Planned Obsolescence Practices in Robotics and What This Means for Cybersecurity](https://www.youtube.com/watch?v=PnVq_ThrDVI&list=PLf4Fnww4KiFdjCAfs04ynv40xbpqFPibm&index=15), BlackHat USA 2021
    - The Data Distribution Service (DDS) Protocol is Critical: Let's Use it Securely! (*to appear*), BlackHat Europe 2021
    - Breaking ROS 2 security assumptions: Targeting the top 6 DDS implementations (*to appear*), ROS-Industrial Conference 2021


### Robot hacks
A non-exhaustive list of robot hacks due to cybersecurity issues.

| Codename | Robots affected | Researchers | Description | Date |
|-----|-------|-------------|-------------|------|
| | [Enabot Ebo Air](https://na.enabot.com/shop/air001) | Modux[^1] |  Researchers from Modux found a security *flaw* in Enabot Ebo Air #robot and responsibly disclosed their findings. Attack vectors could lead to remote-controlled *robot* spy units. Major entry point appears to be a hardcoded system administrator password that is weak and shared across all of these robots. Researchers also found information disclosure issues that could lead attackers to exfiltrate home (e.g. home WiFi password) that could then be used to pivot into other devices through local network. | 21-07-2022 |


[^0]: Read on what a security-first approach in [here](https://www.darkreading.com/edge-articles/a-security-first-approach-to-devops).
[^1]: Serious security issues uncovered with the Enabot Smart Robot https://www.modux.co.uk/post/serious-security-issues-uncovered-with-the-enabot-smart-robot
