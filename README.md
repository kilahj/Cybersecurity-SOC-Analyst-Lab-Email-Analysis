# Cybersecurity-SOC-Analyst-Lab-Email-Analysis


## Objective
- Understand the importance of email analysis in cybersecurity operations, particularly in detecting and mitigating phishing attacks.
- Learn how to investigate phishing emails effectively within a Security Operations Center (SOC) environment.
- Identify common characteristics and indicators of phishing emails.
- Develop skills in analyzing email headers, content, and attachments to determine malicious intent.
- Gain hands-on experience with real-world phishing scenarios to enhance incident response capabilities.
- Explore strategies for phishing email detection, prevention, and response within organizational security frameworks.

### Skills Learned

### Tools Used
- Notepad++
- HxD
- Powershell
- Exif
- SquareX: https://public.sqrx.com/web/
- CyberChef: https://gchq.github.io/CyberChef/
- Gary Kessler file signature : https://www.garykessler.net/library/file_sigs.html

## Scenario
CoCanDa, a planet known as 'The Heaven of the Universe' has been having a bad year. A series of riots have taken place across the planet due to the frequent abduction of citizens, known as CoCanDians, by a mysterious force. CoCanDa’s Planetary President arranged a war-room with the best brains and military leaders to work on a solution. After the meeting concluded the President was informed his daughter had disappeared. CoCanDa agents spread across multiple planets were working day and night to locate her. Two days later and there’s no update on the situation, no demand for ransom, not even a single clue regarding the whereabouts of the missing people. On the third day a CoCanDa representative, an Army Major on Earth, received an email.

## When performing analysis of any kind, it is important to use a VM and not your host machine. 

##
<img width="1440" alt="Screen Shot 2024-05-31 at 1 09 58 PM" src="https://github.com/kilahj/Cybersecurity-SOC-Analyst-Lab-Email-Analysis/assets/99774720/c96d1186-fbbf-4352-aa7b-ddf11b251c51">

- Delivered To: Who received the email
- Received (by): Email servers that received the email (closest to recipient)
- Received (by): Closest to the sender
- X headers: optional, but included by tools or mail servers
- Authenticated Received Chain Header (ARC): verification purpose, trusted intermediate email server, digitally sign the header
- Return-Path: Email used if failed to send (troubleshooting purposes)
- Authentication-Results: status for email protection
- SPF: good indication for suspicious emails. (If SPF is set to fail, may want to analyze the email)
- To: Recipient
- Subject: subject of email
- From: Who sent the email
- Reply To: email address used the moment recipient clicks 'reply to email'
- ContentType: content/format of email
- Message-ID: unique identifier to keep track of email
- Date: when recipient received email (date can be spoofed)
- base64, decode

  
<img width="1435" alt="Screen Shot 2024-05-31 at 1 25 31 PM" src="https://github.com/kilahj/Cybersecurity-SOC-Analyst-Lab-Email-Analysis/assets/99774720/e3682660-b286-49bd-9d0f-569cc6722db9">
#
#

<img width="1440" alt="Screen Shot 2024-05-31 at 1 28 07 PM" src="https://github.com/kilahj/Cybersecurity-SOC-Analyst-Lab-Email-Analysis/assets/99774720/137d3721-4a72-4ff6-95fd-a77c030a6170">

> Email header, converted to Hex and the first few bytes (50 4b 03 04) are called a file signature (file header)
#
#
<img width="1344" alt="Screen Shot 2024-05-31 at 1 31 35 PM" src="https://github.com/kilahj/Cybersecurity-SOC-Analyst-Lab-Email-Analysis/assets/99774720/d9b85a72-c799-43cc-bd53-0d470f34f02b">

> Relates to a .zip file
#
#
<img width="976" alt="Screen Shot 2024-05-31 at 1 32 24 PM" src="https://github.com/kilahj/Cybersecurity-SOC-Analyst-Lab-Email-Analysis/assets/99774720/cf9f7d08-9108-4f82-9d2b-e0d04617baf2">

> Pdf begins with (25 50 44 46)

#
#

<img width="1107" alt="Screen Shot 2024-05-31 at 1 43 57 PM" src="https://github.com/kilahj/Cybersecurity-SOC-Analyst-Lab-Email-Analysis/assets/99774720/6b220709-3e37-4b56-b10c-769a61d3bdbe">

> Extracted files before show hidden items selected
#
#

<img width="1114" alt="Screen Shot 2024-05-31 at 1 45 01 PM" src="https://github.com/kilahj/Cybersecurity-SOC-Analyst-Lab-Email-Analysis/assets/99774720/27bb4316-8262-4e7e-ac5e-d5ed815cd39c">

> Extracted files after show hidden items selected
#
#
<img width="450" alt="Screen Shot 2024-05-31 at 1 51 45 PM" src="https://github.com/kilahj/Cybersecurity-SOC-Analyst-Lab-Email-Analysis/assets/99774720/43e53f6d-af07-45de-8cf4-02342a51fe67">
<img width="450" alt="Screen Shot 2024-05-31 at 1 52 48 PM" src="https://github.com/kilahj/Cybersecurity-SOC-Analyst-Lab-Email-Analysis/assets/99774720/ced111da-080d-4443-bf17-f0d7116394a1">

> Using HxD contents of DaughtsCrown and confirmed the file is a jpeg format

<img width="450" alt="Screen Shot 2024-05-31 at 2 00 04 PM" src="https://github.com/kilahj/Cybersecurity-SOC-Analyst-Lab-Email-Analysis/assets/99774720/0ffd0332-4eba-4c96-bf3b-efd70f2c49a0">

> Confirmed contents were JPEG format

#
#


<img width="450" alt="Screen Shot 2024-05-31 at 1 56 07 PM" src="https://github.com/kilahj/Cybersecurity-SOC-Analyst-Lab-Email-Analysis/assets/99774720/ca78ec87-ae5b-406d-83c6-1caa2774ec4e">

> Contents of GoodJobMajor
#
#


<img width="655" alt="Screen Shot 2024-05-31 at 1 57 37 PM" src="https://github.com/kilahj/Cybersecurity-SOC-Analyst-Lab-Email-Analysis/assets/99774720/d8bceba2-4e57-4379-83b9-ff010a832338">
<img width="816" alt="Screen Shot 2024-05-31 at 1 59 00 PM" src="https://github.com/kilahj/Cybersecurity-SOC-Analyst-Lab-Email-Analysis/assets/99774720/88ee85d0-b389-4a82-822d-9061ae764d26">

> Using Hxd, contents of GoodJobMajor as listed previously were 25 50 44 46, which is a pdf format
#
#


<img width="675" alt="Screen Shot 2024-05-31 at 2 01 44 PM" src="https://github.com/kilahj/Cybersecurity-SOC-Analyst-Lab-Email-Analysis/assets/99774720/8a6ec62a-344d-4f78-8c0a-9fd9d86ff201">

> Using HxD contents of hidden file Money.xlsx
#
#
<img width="921" alt="Screen Shot 2024-05-31 at 2 03 55 PM" src="https://github.com/kilahj/Cybersecurity-SOC-Analyst-Lab-Email-Analysis/assets/99774720/4981dac2-7cd0-40ad-91d0-465f9b18f78c">

> Contents are a Microsoft Excel file

#
#

<img width="1418" alt="Screen Shot 2024-05-31 at 2 09 01 PM" src="https://github.com/kilahj/Cybersecurity-SOC-Analyst-Lab-Email-Analysis/assets/99774720/07b7ac96-0c79-4d3c-9cb2-b04b0d69b8d8">

> Using a file viewer to display contents of file

#
#

<img width="445" alt="Screen Shot 2024-05-31 at 2 11 15 PM" src="https://github.com/kilahj/Cybersecurity-SOC-Analyst-Lab-Email-Analysis/assets/99774720/28d57110-c320-4120-99a3-c9609493d884"><img width="445" alt="Screen Shot 2024-05-31 at 2 12 19 PM" src="https://github.com/kilahj/Cybersecurity-SOC-Analyst-Lab-Email-Analysis/assets/99774720/2d598ed3-4168-4e10-bad3-63e33923df71">

> Sheet 3 is 'blank' after clearing format, a base 64 appears

<img width="583" alt="Screen Shot 2024-05-31 at 2 21 36 PM" src="https://github.com/kilahj/Cybersecurity-SOC-Analyst-Lab-Email-Analysis/assets/99774720/481300e0-4c10-4bb6-859f-8517ea7f78f5">

> Decode of base 64 from CyberChef, with message: "The Martian Colony, Beside Interplanetary Spaceport."

<img width="450" alt="Screen Shot 2024-05-31 at 2 23 53 PM" src="https://github.com/kilahj/Cybersecurity-SOC-Analyst-Lab-Email-Analysis/assets/99774720/1a92db1e-5597-4670-8e6c-70801ace8885"><img width="450" alt="Screen Shot 2024-05-31 at 2 25 14 PM" src="https://github.com/kilahj/Cybersecurity-SOC-Analyst-Lab-Email-Analysis/assets/99774720/129c7bd5-44ec-420d-b769-dcfd5ab6be5d">

> Fake mailer, web based tool to send fake emails

<img width="806" alt="Screen Shot 2024-05-31 at 3 02 24 PM" src="https://github.com/kilahj/Cybersecurity-SOC-Analyst-Lab-Email-Analysis/assets/99774720/be304eda-a0d5-4712-8efd-1c8319d35db8">

> to find the full name of the fake email address, I used Powershell and exif tool to extract the meta data of the files

```sh
PS C:\Users\Kilah> C:\Users\Kilah\Downloads\exiftool-12.85\exiftool.exe -f C:\Users\Kilah\Downloads\attachment\PuzzleToCoCanDa\*
```


## Challenge Questions:
### What is the email service used by the malicious actor? 
emkei.cz
### What is the Reply-To email address?
negeja3921@pashter.com
### What is the filetype of the received attachment which helped to continue the investigation?
.zip
### What is the name of the malicious actor?
Pestero Negeja
### What is the location of the attacker in this Universe?
The Martian Colony, Beside Interplanetary Spaceport
### What could be the probable C&C domain to control the attacker’s autonomous bots?
pashter.com

## More important fields to pay attention to:
- Received: mail servers that received the email. Perform OSINT on the servers, check for sender IP, IP reputation, domain reputation, and email service authenticity.
- Return path : check email address
- Authentication results: check status of
- From - Who sent the email, focus on email address (this can also be spoofed)
- Reply to : From email address and reply to email address may differ (identifier)
- Recipient
- Subject
