# Answer of Questions  
### 1. Many websites expose their “.git” files, please show how it could be dangerous.  
Exposing git file in fact is equal to make your repo public.  
If there is confidential info hardcoded in the source code of websites (e.g. database configs, encryption keys, etc.) it could be very dangerous.  
But if the website doesn't hardcode sensitive information, then it's fine. But keep in mind, by revealing source code of a website, an attacker can achieve more valuable information of website design and it could be so helpful for him/her, such as information about website design. Although in secure software development it is recommended not to follow **Security by Obscurity**.  
### 2. Imagine that we have 2^48 text files. Explain how can we find which files are the same.  
Comparing two set of files is possible via `diff` command. It can be used with `-r` switch in order to compare the content of two folders.  
If the content of aforementioned text files are not small in size, generating cryptographic digests (by using **hash functions**) of files can be useful. Thus we can compare digests instead of comapring the whole files.  
