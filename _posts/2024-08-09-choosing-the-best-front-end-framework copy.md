---
layout: post
title: 'CRTO (Certified Red Team Operator) Review - July 24'
tags: [RedTeam, CRTO]
featured_image_thumbnail:
featured_image: /assets/images/posts/2024/RedTeam.jpg
featured: true
hidden: true
---

I just completed the CRTO exam last weekend! How the exam panned out was vastly different from my expectations, so I wanted to share my thoughts to hopefully provide some guidance to others preparing for the exam. Before diving into that, I’ll start with some background.

## Introduction
The CRTO course is being offered by **Zero-Point Security (ZPS)**, and the course materials are prepared and delivered by RastaMouse (aka Daniel Duggan). I enjoyed the course/labs/exam and found what I learnt to be relevant to my day job.

## My background coming into the CRTO course
Prior to the CRTO, I have done a couple of certifications geared towards pentesting (OSCP, eCPPT, eJPT), and the knowledge I had beforehand definitely came in handy (e.g. pivoting, the concept of reverse vs bind shell, etc). That said, the CRTO is on a different level due to the need for OPSEC and bypassing defenses, and when I was taking the CRTO course, I felt that it nicely built upon my previous knowledge.

## Some definitions before proceeding
Most people new to cybersecurity may assume that Red Teaming == Active Directory (AD) pentesting. At least, that’s what my assumption was a few years ago when I was new to the field, as certifications covering AD pentesting were typically being marketed as red teaming certifications, leading to misconceptions and usage of the two terms interchangeably. In my humble opinion, red teaming includes the testing of people, processes, and technologies, and a significant portion of red teaming involves some degree of stealth to reduce the risk of getting caught by the defensive mechanisms in place. Hence, Red Teaming does not have to involve AD pentesting. Sure, stealthily moving through a corporate network which happens to be using AD is considered red teaming, but again, AD is not a prerequsite of Red Teaming.

With that out of the way, the following is a summary of my experience going through the CRTO course and exam.

## What CRTO covers
The course goes through each stage of the attack lifecycle (think initial access, persistence, privilege escalation, domain reconnaissance, domain dominance, exfiltration, etc) which includes different ways of attacking AD. Towards the end of the course, it also includes tips on improving OPSEC and basic techniques on how to bypass defences. The C2 used is Cobalt Strike, a commercial tool widely used by red teams and APT groups alike.

**Structure of the course**:

First, students go through the lab (Windows Defender is switched OFF) to familiarise themselves with how to carry out the techniques in the attack chain.
Nearing the end of the course, the final module provides some instructions on how to enable Defender on all machines in the lab, and advises the student to go through the entire lab again.
Bonus: Elastic has also been set up in the lab, and there are certain sections in the course material that covers how to query for malicious activities that you as the Red Team Operator has executed. Pretty neat.
The course gives step-by-step commands/instructions at the start and moves towards being more hands-off towards the end of the course, which was helpful as it forced me to think more critically and fill in the gaps myself based on what was covered in the earlier parts of the course.

Side note: So… I bought the course back in August 2021 and was doing it on/off due to other conflicting priorities. Back then, we could purchase lab time without any expiry date, which also led to me dragging it out lol. I actually picked up the course 2–3 times over the past 2 years and did it till 50% completion but never finished it. In any case, I decided to hunker down and complete it in 2023 and yay, mission accomplished! One thing I noticed over the few times of going through the course is that it does update quite frequently, which I absolutely appreciate. Not a lot of course creators out there would take the time and effort to update at this frequency, unless it has been a good few years and the material became outdated. (Currently, CRTO lab purchases have switched to a subscription model. It is very affordable at £20 for 40h of lab time, which will expire 1 month from when you purchase it. You can purchase lab time here.)

A few weeks before the exam, I read through a few CRTO reviews and most mentioned that they were able to pass on the 1st day, making it sound like a breeze. I got complacent and did not prepare enough, and this led to me being an anxious ball of stress during the 4-day period of the exam, lol. Looking through the Zero-Point Security discord, I was surprised to see quite a few comments from others who failed the exam and decided to retake it. I guess there is a form of survivorship bias at play too, in that exam reviews are typically posted by those who may have had a relatively easier time in the exam. Hopefully this review provides some insight from a different perspective.

## CRTO exam experience
To pass the exam, you’ll need to obtain 6 out of 8 flags. No report writing is required. The exam spans 4 calendar days, and we are given 48 hours of time in the exam lab environment. I spent about 3.5 days on the exam, and used up ~35 hours of exam lab time (that said, I did leave the exam lab running when I went on breaks). I actually learnt a lot more during the exam itself than when I was going through the course, since troubleshooting why certain commands/techniques did not work helped me better understand why they worked the way they did.

The exam was fun. It wasn’t as straightforward as I thought it would be, so some creative thinking helped me out. Having Defender enabled threw a wrench into things at times, but with enough head bashing against the keyboard, you can do anything. I had to refer to some external materials during the exam, but I believe if you redid the entire lab with Defender enabled, you probably would have been sufficiently prepared and not have to refer to external materials.

For the sake of not spoiling the exam, I won’t go into a day-by-day replay. Summary: I was stuck on getting the 5th flag for a long time due to something I overlooked, which in hindsight is facepalm-worthy. Once I got the 6th flag after ~30h in the exam lab environment, I heaved a sigh of relief and decided to call it a day.

10 minutes after the end of the 4 calendar days, this badge arrived in my email:


Certified Red Team Operator badge
Of note, the exam was using Cobalt Strike v4.8 when I took it on 2 June, and the course material and lab had just updated on 22 May. There were some additional modules/edits to existing modules in the course, and I managed to go through the new material before sitting for the exam. As the content was new, I went through some trial and error to troubleshoot certain commands, and thankfully managed to figure it out just in time for the exam.

## Hindsight is 20/20
Tips I wish I knew before starting the exam:

When going through the lab, take time to understand the attacks, including the pre-requisites needed for each attack, and which kinds of situation call for which attacks. Don’t just run the commands and call it a day when it works on the first try.
As you go through the lab, draw out network diagrams of how the machines in the lab are connected to each other. This will help you get familiar with how to pivot properly using Cobalt Strike.
It is highly recommended to go through the entire lab again after switching on Defender. My mistake was going through only ~25% of the course again with Defender enabled, which in hindsight was definitely not enough.
We are able to copy text from the exam environment and paste it in our host machine. Don’t be like me who manually typed out the contents of the flag when submitting it 🫠

## Support
As with most certifications/courses, support is super important in ensuring one’s success (along with minimising frustration). There is one person from ZPS managing support, and that’s Rasta. In my experience, there is quick turnaround regarding administrative issues e.g. lab time reset (he once replied my email in 10 minutes when I had some lab time issues). However, for questions relating to the course material itself, it’s best to seek for help in the discord. There are plenty of helpful folks there, and as long as your question is asked clearly with proper screenshots/error messages, you will likely get a response. From past discord replies, you’ll also be able to look at common errors made by those before you to help you should you face the same issue. In fact, when the course material updated in late-May, there were some parts of the new material that were clarified by other students in the discord, which helped immensely. There is also the community channel (My Communities > Red Team Ops) on the ZPS site itself, although I’ve never used it.

## Conclusion
If you are interested in red teaming, I highly recommend purchasing the CRTO course. The course and labs (currently v2.1.2) comes with lifetime updates. As I went through the course materials a few times since August 2021, I actually learnt something new from each different version of the course. For the price of £365, it’s a steal. There is also an option to purchase lab time whenever, so even if you have finished the course/exam, you can always decide to purchase lab time in the future when the course goes through further updates, for your own experimentation. Having access to Cobalt Strike in the lab is also a huge bonus as it might be difficult to get your hands on a Cobalt Strike installer as an individual (compared to open-source C2 tools).

Thanks for reading all the way till here, hope this was useful. If you decide to take the CRTO, all the best and enjoy!