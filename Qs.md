# Answer of Questions  
### 1. Many websites expose their “.git” files, please show how it could be dangerous.  
Exposing git file in fact is equal to make your repo public.  
If there is cinfidential info hardcoded in the source code of websites (e.g. database configs, encryption keys, etc.) it could be very dangerous.  
But if the website doesn't hardcode sensitive information, then it's fine.  
It's worth stating that by revealing source code of a website, an attacker can achieve more valuable information of website design and it could be so helpful for him/her.  
Although in secure software development it is recommended not to follow **Security by Obscurity**.  