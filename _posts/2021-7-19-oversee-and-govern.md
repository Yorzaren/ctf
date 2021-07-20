---
title: "CyberForce 2021 - Oversee and Govern"
categories:
  - CyberForce
tags:
  - CyberForce
  - CyberForce-2021
  - CyberForce Adventurer
---

# Oversee and Govern

## Oversee and Govern: Anomaly 7 (20pts)
Identify the NIST subcategory that best aligns with the situations below:

(1) In response to a phishing attack, a company releases a statement reaffirming the security roles and responsibilities for the employees.

(2) Upon a DDoS attack, company officials identify weak spots in their defense, and locate spaces where traffic infiltrated. In addition, resources most impacted are assessed. In response, the company decides to update its DDoS defense at vulnerable points for future incidents.

syntax hint: Leave a single space between each answer, and use a XX.XX-Y format. 

e.g., AB.AC-# AB.AB-#

## Oversee and Govern: Anomaly 12 (20pts)
You manage a team of cybersecurity experts.  Two members of your team are senior level and three are junior level.  Your team handles the following tasks: 
```
•	Responding to incidents 
•	Hunting 
•	Development 
•	Research 
```
Senior level cyber experts are twice as effective as junior members at hunting and development but are no more effective at responding to incidents and research.  All the tasks except for research must be performed or the consequences are dire 

Blake, one of your junior cyber experts wants to take vacation next week.  You have forecast the workload for next week as follows (hours normalized to junior level of effort): 110 hours for responding to incidents, 70 hours for hunting, 60 hours for development, any remaining time can be spent on research.   Assuming each expert has 40 hours per week what is the maximum number of hours that Blake can take for vacation without dire consequences?

syntax hint: the answer is a number

### Solution

So: You have 5 members 2 are seniors and 3 are juniors. One junior wants to take off work for the week. 

This makes the working members 2 seniors and 2 juniors. Each member has a max of 40hr so 4x40 = 160hrs

Critical tasks are:
```
RI - 110
H* - 70
D* - 60

* Sr bonus reduces the time by half.
```

S1 can do 30hr of D and which is worth 60hrs meaning D is done.

Leaves S1 with 10hrs of work left.

Assign S1 to H for 10hrs which does 20hrs of work meaning H need 50hrs more. S1 can't work anymore.

S2 can do 25hrs of work on H doing 50hrs worth meaning H is done. S2 has 15hrs left of work in them.

15+40+40 (from the other two juniors) = 95 remaining hours.

110-95 = -15. You need the 3rd junior to work 15hrs of the 40 week meaning he can take off 25hrs.

Ans: `25`

## Oversee and Govern: Anomaly 18 (20pts)
You have been asked to help with the development of your organization’s overall security policy. You have been tasked with contributing towards the cyber policy for supply chain management at the organization. In particular, your manager wants to see some sort of policy created that will allow the cyber team to bear less of the responsibility for risks associated with vendors. You found a case study that was published by NIST that described the best practices of a large energy company. After looking at the provided document, what is the name of the internal cyber policy that would require non-cyber employees to accept responsibility if they needed to use a riskier vendor?

Syntax hint: answer is not case sensitive

## Oversee and Govern: Anomaly 25 (20pts)
You work on the security team at Captain Trips Financials. A software requisition has been put in to migrate the company’s video conference software over to Zoom. The standard operating procedure for software requisitions requires the security team to perform a security assessment to make sure the requested application meets the company’s security policies and standards. 

Your task is to use the provided Software Security Assessment Methodology document to perform a high-level assessment of Zoom. The document details how to use the methodology, and how you will derive your answer by using it. 

Syntax hint: answer is not case sensitive, no spaces, include dashes

## Oversee and Govern: Anomaly 31 (20pts)
According to the 2017 OWASP Top 10 list, there are a few new additions to the top 10 since the 2013 version. Of those, what is the name of the vulnerability that typically involves a web application accepting direct uploads or data to be inserted to be parsed in a specific file format?

syntax hint: answer is not case sensitive, include spaces. E.g., Apples Bananas Oranges

## Oversee and Govern: Anomaly 39 (20pts)
In the NIST Digital Identity Guidelines, which Authenticator Assurance Level requires two factors of authentication?

syntax hint: numerical answer

### Solution

Ans: `2`

## Oversee and Govern: Anomaly 40 (20pts)
In the NIST Security and Privacy Controls for Federal Systems, which family of controls encompasses Information Flow Enforcement?

syntax hint: answer is not case sensitive, include space in between words. E.g., Apple orchard

### Solution

Ans: `Access Control`

## Oversee and Govern: Anomaly 41 (20pts)
What regulation provides data protection and privacy for all individual citizens of the European Union and the European Economic Area? 

Syntax hint: full name, no acronyms

### Solution

Ans: `General Data Protection Regulation`

## Oversee and Govern: Anomaly 42 (20pts)
A _____ policy is a statement or a legal document that discloses some or all of the ways a party gathers, uses, discloses, and manages a customer or client's data. 

### Solution

Ans: `privacy`

## Oversee and Govern: Anomaly 43 (20pts)
COMSEC comprises which four speciality areas? 

Syntax hint: Please list the word only, in alphabetic order. Do not tack on "security" at the end of any of these words, and answer in the format Apple, banana, grape, orange

### Solution

Ans: `Cryptographic, emission, physical, transmission`

## Oversee and Govern: Anomaly 52 (20pts)
Identify the correct Work Role ID from the NIST NICE Framework from the descriptions provided below. Please enter the Work Role ID exactly as it is formatted in the Framework (XX-XXX-XXX). (https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-181.pdf) 
a.	This person is primarily responsible for overseeing compliance staff and ensuring the team has what they need to maintain privacy
b.	This person might work closely with the Information Systems Security Officer to plan and make decisions based on cyber operations at an organization. They are likely the main representative for the cyber security team, and their main goal is to convey the organizations cybersecurity plan among executive leaders. 
c.	Your organization had annual cybersecurity training. This individual is responsible for delivering content via video trainings to all staff members. 

syntax hint: format answers as the following:
e.g., AB-CDE-###, FG-HIJ-###, LM-NOP-###

## Oversee and Govern: Anomaly 53 (20pts)
These questions pertain only to the NIST Cyber security Framework. Please provide the unique subcategory ID that alights best with the description. (XX.XX-X)
1.	Your site contains barriers, fences, security cameras, and other controls to de-incentives adversaries from unauthorized access. 
2.	 Once a month, IT and OT system administrators scan and inventory all devices on site. New devices are provided a unique barcode, and old devices are handled appropriately. 
3.	  The internal network at your site has an intrusion detection system and  intrusion prevention system, along with full packet captures available for analysis in the event of an incident. 
4.	In responding to an incident, analysts are reviewing logs, obtaining disk images and/or memory dumps of compromised machines, and creating timeline to better understand what happened. 

Syntax hint:
Format your answers in the following way:
AB-CD-#, EF-GH-#, IJ-KL-#, MN-OP-#

## Oversee and Govern: Anomaly 74 (20pts)
This framework provides a six step process that integrates security and risk management into the system development life cycle. It takes into account FIPS 199 & 200 as well as many NIST Special Publications.

Syntax hint: answer is not case sensitive, include spaces, no commas

### Solution

Ans: `Risk Management Framework`

## Oversee and Govern: Anomaly 75 (20pts)
In the original Bloom’s Taxonomy, knowledge, comprehension, application, analysis, synthesis, and evaluation were the main six categories. In the revised taxonomy, the six categories are: remember, understand, analyze, evaluate, create, and what?

Syntax hint: answer is not case sensitive, no spaces, one word answer

### Solution

Ans: `Apply`

## Oversee and Govern: Anomaly 76 (20pts)
This framework, which we utilize throughout this competition, provides a blueprint to categorize, organize, and describe cybersecurity work into categories, specialty area, work roles, tasks, and knowledge, skills, and abilities. Most people know it as the NICE Framework. What does NICE stand for?

Syntax hint: answer is not case sensitive, include spaces, no commas

### Solution

Ans: `National Initiative for Cybersecurity Education`

## Oversee and Govern: Anomaly 77 (20pts)
Utilizing the Zachman Framework, if I wanted to identify the detailed who of my enterprise architecture, what would I need to provide.

Syntax hint: include a space between words, not case sensitive

## Oversee and Govern: Anomaly 78 (20pts)
Encryption falls under the U.S. Commerce Control List. This list is broken into 10 categories. What category number does encryption fall under? 

Syntax hint: Please use numbers only

### Solution

Ans: `5`

## Oversee and Govern: Anomaly 93 (20pts)
What assessment and authorization process is used by federal agencies to ensure the security of cloud service providers?

Syntax hint: answer is not case sensitive, no spaces

### Solution

Ans: `FedRAMP`

## Oversee and Govern: Anomaly 71 (50pts)
Decrypt the following file with my public key. Key ID 2E33D58C

Inside the text file, reads the following text:
If I want to send a message to Amanda to ensure confidentiality and integrity, which option would work best?
A) My public and my private key
B) My private key and Amanda’s public key
C) My public key and Amanda’s private key

syntax hint: Enter in the letter (A, B, Or C) to the scoreboard for points for this anomaly.

### Solution

Recall:
```
Summary Public key cryptography

Public key cryptography provides the basis for securely sending and receiving messages with anyone whose public key you can access.
 
Public keys enable:
Users to encrypt a message to other individuals on the system
You can confirm a signature signed by someone’s private key
Private keys enable:

You can decrypt a message secured by your public key
You can sign your message with your private key so that the recipients know the message could only have come from you.
```
From https://www.preveil.com/blog/public-and-private-key/

Ans: `B`