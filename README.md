# 🎣Phishing Simulation for Security Awareness Using Zphisher

## Introduction

Phishing is a type of cyber attack where attackers trick individuals into providing sensitive information, such as login credentials, financial details, or business data, by impersonating a trustworthy entity. This is usually done through fraudulent emails, messages, or websites designed to look legitimate.

## Objectives

Demonstrate how attackers create fradulent emails, messages and login pages to capture user credentials using phishing tools such as Zphisher.


## Tools 

Zphisher - to create phising login pages. It is an automated phishing tool that offers phishing templates for 33 popular websites.

Kali Linux - VM we will use to download Zphisher.

Email - craft email content that will increase the likelihood of recipients opening the emails and clicking on the links.


## ⚠️ Important ⚠️
**If you’re using Zphisher for educational purposes, ensure that:**

✅ You have explicit permission from your organization or training participants.

✅ It is done in a safe lab environment (not on live networks or real accounts).

✅ No personal data is misused.


## Part 1 – Installing and Configuring Zphisher

1. Before downloading Zphisher, update Kali Linux terminal by running the following commands and to ensure that environment was conducive for Zphisher to function
   - sudo apt update
   - sudo apt full-upgrade -y

2. Create Zphisher directory and navigate into it using the following commands in succession.
   - mkdir zphisher
   - cd zphisher

![alt zphisher](https://github.com/ayushmak7/Phishing-Tool-Implementation/blob/main/images/1.png?raw=true)

3. Install & Set Up Zphisher
   - Install necessary dependencies.
   - Clone the Zphisher repository using this url https://github.com/htr-tech/zphisher.git and launch the tool.
  
![alt zphisher](https://github.com/ayushmak7/Phishing-Tool-Implementation/blob/main/images/3.png?raw=true)


4.  Navigate to the downloaded “zphisher” directory to see the files within by running the following commands:
      - cd zphisher
      - ls

![alt zphisher](https://github.com/ayushmak7/Phishing-Tool-Implementation/blob/main/images/4.png?raw=true)


5. Run the Zphisher script (contained in the zphisher.sh shell script file) by executing the following command:
      - bash zphisher.sh

![alt zphisher](https://github.com/ayushmak7/Phishing-Tool-Implementation/blob/main/images/5.png?raw=true)


6. A page opens with phishing page templates giving options of the type of phishing attacks that to can be performed by entering the corresponding number.

      - Upon typing the preferred option (e.g.14) against the “select option” prompt

 ![alt zphisher](https://github.com/ayushmak7/Phishing-Tool-Implementation/blob/main/images/6.png?raw=true)


7. Zphisher provides three tunneling options: Localhost, Cloudflared, and LocalXpose.

   - Localhost allows you to access your local server using a local IP address, typically 127.0.0.1 or localhost and is useful for testing your server on your own machine.
   - Cloudflared exposes your local server to the internet using a secure tunnel. It is useful for accessing your server from anywhere, while keeping your traffic encrypted.
   - LocalXpose uses LocalXpose's reverse proxy to expose your local server to the internet. This is similar to cloudflared, but with a simpler setup process. 

![alt zphisher](https://github.com/ayushmak7/Phishing-Tool-Implementation/blob/main/images/8.png?raw=true)



Tunneling in the context of Zphisher package refers to the process of exposing a local server running on your machine to the internet. This allows you to access your local server from anywhere in the world, as if it were a public server.
  

Upon typing the preferred option (e.g.1) for the “port forwarding service” or tunnelling option prompt, a [y/N] (Yes or No) prompt to choose or use a custom port will appear.
Upon typing the preferred option (e.g. n for No) in response to the question “Do you want a Custom Port [y/N]”, the following output will be displayed.




It confirms launching Cloudfared and initializes (http://127.0.0.1:8080), which directs the browser to make a TCP connection to port 8080 of the local loopback address 127.0.0.1 known as "localhost". The loopback address is a special IP address that always refers back to the current device, allowing it to connect to itself.

Next is another Yes or No prompt (Do you want to change the Mask URL? [y/N) for the URL you want to use for the phishing page. A Yes answer means you provide the URL of your choice while a No answer means you use the default URL provided by Zphisher:



The tool provides Mask URL options that you can use or use a custom one. The option chosen was a Zphisher provide Mask URL. When copied and pasted onto a browser page, it opened a Linkedin login page that appeared legitimate. The user name and the password you type in will be harvested in the zphisher tool.




Once the victim enters their credentials, they will be displayed in the terminal as shown in the two images below:



The image above containing credentials identical to the preceding image represents credentials harvested from DEO Gumba’s network. 


Part 3 – Testing the Vulnerability

After testing that Zphisher worked, I sent the same URL to Ayushma Koirala, who logged in successfully to the fake Linked-in page, which appears legitimate. The image below represents credentials harvested from her network.



When you the phishing email with the generated phishing link is sent to the target, they will click on the masked URL instead of the actual phishing URL. If the masked URL leads to a malicious website, it can potentially deceive them into trusting the malicious website, potentially resulting in them falling victim to a phishing attack and their credentials being harvested in realtime on zphisher.


Part 4 – Project Preparation

To ensure all worked as expected within the very limited presentation time, it was more feasible to record a video showing how we harvested the credentials and then demonstrate prelude the video with a power presentation that we would be in control of.

We practiced this procedure several times to before recording the video to confirm that the presentation would run smoothly when we ran it for recording.

We put together a slide deck with images and videos illustrating:

Why we chose social engineering (phishing) attack?
Phishing tools usage in penetration testing
Zphisher as a phishing tool
Key features of Zphisher
Source of Zphisher
Demo preview: Installation
Demo preview: Kali Linux tool
Zphisher - Disclaimer
Zphisher Demo video
Outcome of the attack - Captured credentials (Deo’s network)
Outcome of the attack - Captured credentials (Ayushma’s network)
Mitigating phishing attacks

Part 5 – Mitigating Phishing Attacks

By implementing a multi-layered defence strategy that includes staff education, regular simulated phishing campaigns, email filtering tools, DMARC records, multi-factor authentication (MFA), separate work and personal devices, established mail providers like Gmail or Office 365, and access control and privilege management policies, organizations and individuals can reduce the risk of phishing attacks and protect their sensitive information.


Conducting staff education is a critical component of phishing attack mitigation. Employees should be trained to recognize and respond to phishing attacks, including how to identify suspicious emails, how to verify the sender's identity, and how to report phishing attempts. 
Regular simulated phishing campaigns can help employees stay vigilant and improve their phishing recognition skills.
Implementing email filtering tools can help detect and block phishing emails before they reach the user's inbox. These tools use a variety of techniques, such as machine learning algorithms, reputation analysis, and content analysis, to identify and filter out phishing emails.
Publishing DMARC (Domain-based Message Authentication, Reporting, and Conformance) helps prevent email spoofing and phishing attacks. By publishing a DMARC record, organizations can specify how their email domains should be authenticated and what should happen to unauthenticated emails. This can help prevent attackers from sending phishing emails that appear to come from a legitimate domain. The DMARC record specifies the policy for handling emails that fail the authentication checks, such as quarantine or reject. 
Implementing multi-factor authentication (MFA) will ensure that users to provide multiple forms of authentication before accessing a system or application. This can include something the user knows (such as a password), something the user has (such as a security token), or something the user is (such as a biometric factor). MFA can help prevent attackers from gaining access to sensitive information, even if they have obtained the user's password.
Implementing separate work and personal devices policy can help prevent attackers from gaining access to sensitive information through personal devices that may not have the same level of security as work devices. This can include using separate devices for work and personal email, social media, and other online activities.
Using established mail providers like Gmail or Office 365, to offer advanced security features that can help detect and block phishing attacks. These features may include email filtering, spam blocking, and anti-phishing tools.
Implementing access control and privilege management policies can help prevent attackers from gaining access to sensitive information by limiting access to authorized users and devices. This can include implementing role-based access control (RBAC), which restricts access to specific roles or job functions, and implementing least privilege principles, which limit access to the minimum level required to perform a task.

References

Anderson Tiffani (July 27, 2023). What Is URL Masking and When Should You Mask a Link (bluehost.com) https://www.bluehost.com/blog/everything-you-need-to-know-about-url-masking/

Cloudfare (January 2024) Set up your first tunnel · Cloudflare Zero Trust docshttps://developers.cloudflare.com/cloudflare-one/connections/connect-networks/get-started/

CrowdStrike (February 13, 2023). How To Implement Phishing Attack Awareness Training (crowdstrike.com) https://www.crowdstrike.com/cybersecurity-101/phishing/phishing-attack-awareness-training/

DMARC. dmarc.org – Domain Message Authentication Reporting & Conformance https://dmarc.org/

Emelianov David (November 18, 2023). Business Email Filtering Tools: A Comprehensive Guide (trimbox.io) https://www.trimbox.io/blog/business-email-filtering-tools

GitHub  (2024) - htr-tech: Automated phishing tool with 30+ templates. https://github.com/htr-tech/zphisher  

Heimdal (December 7, 2023). What Is a Privileged Access Management Policy? Guidelines and Benefits (heimdalsecurity.com). https://heimdalsecurity.com/blog/what-is-a-privileged-access-management-pam-policy/#:~:text=How%20to%20Create%20a%20Privileged%20Access%20Management%20Policy,...%206%20Create%20an%20Incident%20Response%20Plan%20

InfoSec Pat on Youtube (2023). How to Install and Run Zphisher on Kali Linux Phishing Tool - Video 2023 with InfoSec Pat. https://www.youtube.com/results?search_query=How+to+Install+and+Run+Zphisher+on+Kali+Linux+Phishing+Tool+-+Video+2023+with+InfoSec+Pat+   

Johnson Ann & Morillo Christina (January 17, 2020). How to implement Multi-Factor Authentication (MFA) | Microsoft Security Blog https://www.microsoft.com/en-us/security/blog/2020/01/15/how-to-implement-multi-factor-authentication/

MacKay James. How To Run A Successful Phishing Simulation Campaign (metacompliance.com) https://www.metacompliance.com/blog/phishing-and-ransomware/run-phishing-simulation-campaign

Mell Peter & Grance Tymothy (September 2011). Recommendations of the National Institute of Standards and Technology NIST US Department of Commerce https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-115.pdf

Mystrika (2024). Cold Email: Setting Up Your Own Email Server Vs Established Email Service Provider - Mystrika - Cold Email Software. https://blog.mystrika.com/cold-email-setting-up-your-own-email-server-vs-established-email-service-provider/

Nelson, N. (2024, April 19). LastPass users lose master passwords to ultra-convincing scam. Dark Reading. https://www.darkreading.com/cyberattacks-data-breaches/lastpass-users-lose-master-passwords-ultra-convincing-scam  

Smith, G. (2023, October 23). Top Phishing Statistics for 2023: Latest Figures and Trends. StationX. https://www.stationx.net/phishing-statistics/
