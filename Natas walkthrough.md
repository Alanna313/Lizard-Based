![OTW](https://user-images.githubusercontent.com/31714690/167018691-b3cfb1f9-6843-4651-832f-a48a86b3affc.PNG)
# Natas walkthrough 1-20  
  Each level of natas consists of its own website located at http://natasX.natas.labs.overthewire.org, where X is the level number. There is no SSH login. To access a 
  level, enter the username for that level (e.g. natas0 for level 0) and its password. Each level has access to the password of the next level. Your job is to somehow 
  obtain that next password and level up
  
# Natas1  
![lvl1 prob](https://user-images.githubusercontent.com/31714690/167219207-7205a7bd-465f-4ea3-895e-4afa7e8c1d12.png)

-The problem: Get to the source code with rightclicking being blocked.

-The Solution: To view the page's source code, on your browser you can clck CTRL + U on your keyboard.

![lvl 2 solution](https://user-images.githubusercontent.com/31714690/167219243-716a894d-000e-449a-be99-fa3b2009a162.png)

# Natas2  
![level 2 prob](https://user-images.githubusercontent.com/31714690/167219416-fab4d729-dac6-4844-95cf-c13c70046af3.png)

-THE PROBLEM: When you first load the page you are given a message that says “There is nothing on this page”. That means there could be other pages on this site but 
there are no buttons to navigate anywhere

-THE SOLUTOIN: Looking through the page source you see that there is a PNG image located in this path “files/Pixel.png”. We added a “/files” at the end of the URl to 
navigate to the files directory. Now we are able to see what's inside that directory and see that there is a “users.TXT” file. Inside that file we found usernames 
and passwords.

![level 2 path](https://user-images.githubusercontent.com/31714690/167219597-41b8ee80-693d-4238-8c68-3e48cfa1692a.png)

![level 2 files](https://user-images.githubusercontent.com/31714690/167219622-0d0378a4-c271-4110-ad54-752841dfabe1.png)

![levl 2 answer](https://user-images.githubusercontent.com/31714690/167219625-963e49ed-5fb7-4050-8c46-390b40151b6a.png)
  
# Natas3  
![level 3 prob](https://user-images.githubusercontent.com/31714690/167219876-dc3a11d5-f114-420d-9e83-b4a325d6dac8.png)

-THE PROBLEM: nothing on the page but a few texts.
  
-THE SOLUTION: In the source code on this site it says “No more information leaks!! Not even Google will find it this time..."
Robots.txt files indicate whether certain user agents can or cannot crawl part of the website. So we checked for robots.txt on this site and we found that there is 
a directory that is not allowed for viewing “s3cr3t”. We navigated to that directory and found another user.txt file with the password to the next challenge

![level 3 robots](https://user-images.githubusercontent.com/31714690/167220109-17f07285-4358-4992-b1e1-8da810cdd6be.png)

![level 3 files](https://user-images.githubusercontent.com/31714690/167220122-8d8f917e-fd11-40b1-ae47-47393e6027a6.png)

![level answer](https://user-images.githubusercontent.com/31714690/167220134-2ff8eb48-6890-400d-98f2-1b341dcc3929.png)

# Natas4  
![level 4 prob](https://user-images.githubusercontent.com/31714690/167220253-bb766fd3-f127-4af9-986d-e9ee3938e8ba.png)

-The problem: Access Disallowed. Authorized user should come from “http://natas5.natas.labs.overthewire.org”

-The Solution: We created a Python script to change the referrer of the request. We ran the Python script and got the password for the next challenge. You can also 
do this by installing a referer control extension for your browser.

![level 4 script](https://user-images.githubusercontent.com/31714690/167220304-f2d6b092-6f15-45ee-851c-f16ae1d84303.png)

![level 4 answer](https://user-images.githubusercontent.com/31714690/167220328-338a393b-60fe-4b17-bb76-353bddb5af52.png)


# Natas5  
![Level 5 prob](https://user-images.githubusercontent.com/31714690/167220454-6c544bfb-5da9-4156-b788-9023909ddda2.png)

-The problem: Access Disallowed. You are not logged in. 

-The Solution: Noticed that the cookie for loggedIn was set to 0, we changed that to 1  using the debugger built into Mozilla Firefox and refreshed the page.

![level 5 inspect tool](https://user-images.githubusercontent.com/31714690/167220508-d8a29aa9-a1b5-4978-add8-543e2166fcb7.png)

![level 5 cookie](https://user-images.githubusercontent.com/31714690/167220523-03bef520-730e-4f0e-b38f-03b7c13a9047.png)

# Natas6
![level 6  prob](https://user-images.githubusercontent.com/31714690/167220627-723dcc45-df2b-4dfd-bcd1-eb62aa9c56df.png)

-The problem: Input Secret to get the answer

-The Solution: Looking through the source code we noticed that there was a file path “includes/secret.inc”. We added that to the end of the URL and came to a page with the secret code. We added that code into the Input query bar and got the next password.

![lvl 6 source code](https://user-images.githubusercontent.com/31714690/167220666-0bf60322-b1b7-4863-a6f8-8e16c52a7c5e.PNG)

![lvl6 answer](https://user-images.githubusercontent.com/31714690/167220688-7557b703-c54c-43df-84f1-e91214aaf7db.PNG)

![lvl 6 password](https://user-images.githubusercontent.com/31714690/167220714-28e47414-33a3-4061-86c2-e2dc5e7e55f2.PNG)


# Natas7  
![lvl 7 home page](https://user-images.githubusercontent.com/31714690/167220749-45fbb080-78f0-4b53-b66f-bd0628693f27.PNG)


-The problem:	Was provided two links to random pages.

-The Solution: Looked at the source page and was provided a hint that the password for the next level was in /etc/natas_webpass/natas8. When we went to one of the 
links we noticed that the index.php took the name of the page as a variable. Since we know where the password is located we try doing a Path Traversal attack(also 
known as directory traversal).  

![lvl 7 path traversal](https://user-images.githubusercontent.com/31714690/167220823-175d8bad-5c1d-483a-b465-22088fc8948f.PNG)

![lvl 7 answer](https://user-images.githubusercontent.com/31714690/167220838-06281799-db35-4cad-bca3-3fbe374cb1cf.PNG)

# Natas8  

![lvl 8 home page](https://user-images.githubusercontent.com/31714690/167220881-70a1968c-4da6-4bfd-a8cb-b5ba70f68adb.PNG)

-The problem: Need to find secret to input for answer

-The Solution: Looked at the source code. There is an encoded secret code provided, used CyberChef to reverse it and get the code. 
![lvl 8 page source](https://user-images.githubusercontent.com/31714690/167220933-aa00e590-ae91-4191-a6c5-eb00e93828c7.PNG)

![lvl8 secret](https://user-images.githubusercontent.com/31714690/167220937-d4b0dc1a-881a-48ca-a1fa-a0ac3e796022.PNG)

![Level 8 answer](https://user-images.githubusercontent.com/31714690/167220980-83c2f4ad-cacc-43c2-b0ca-d7aee67a67e6.png)


  
# Natas9  
![Level 9 prob](https://user-images.githubusercontent.com/31714690/167221028-6019a1c6-c79c-4372-8190-b2c98062aa00.png)


-The problem: Given a search bar that gives results based on a word entered. 

-The Solution: Looked at PHP code in the page source. Noticed possibility of command injection. In the search bar we inserted ‘; cat /etc/natas_webpass/natas10’ 
this is possible because ‘;’ separates commands in a shell.

![lvl 9 php code](https://user-images.githubusercontent.com/31714690/167221174-1bb07ba1-fdd7-4cc1-85c4-5bfe778b6759.PNG)


![Level 9 answer](https://user-images.githubusercontent.com/31714690/167221203-d281af59-981a-441b-a729-f2338a719f49.PNG)

# Natas10  
![lvl 10 home page](https://user-images.githubusercontent.com/31714690/167221221-1042a3d1-c788-4256-bd9d-1f94761a9fd2.PNG)


-The problem:

-The Solution:

![lvl 10 php code](https://user-images.githubusercontent.com/31714690/167221242-bd7dd9a6-87b7-47da-b7fb-26d0d12b5bbf.PNG)

![Level 10 answer](https://user-images.githubusercontent.com/31714690/167221266-73d8d188-eda0-42cd-abb3-b79fe17e1407.png)

# Natas11  

![lvl 11 home page](https://user-images.githubusercontent.com/31714690/167221284-40723ece-17c8-41cb-8cc9-44a16dba9e6a.PNG)

-The problem: Search bar to look for background color.

-The Solution: The data for this one is stored in an array named data. If the data from the array ‘showpassword’ is set to yes we receive the password.To do this we 
have to go into the source code. When we look closer we find a variable called cookie. If we look at the site and look for document.cookie in the developer tools we 
get a string of characters data=ClVLIh4ASCsCBE8lAxMacFMZV2hdVVotEhhUJQNVAmhSEV4sFxFeaAw%3D. The temp data shows us that this is JSON then XOR'd and then encoded 
into base 64. Decoding these in python using the key we were given we get the key of “qw8Jqw8Jqw8Jqw8Jqw8Jqw8Jqw8Jqw8Jqw8Jqw8Jqw”. Now we use this to encode “yes” 
in a cookie on the site, giving us our password for the next level.
  
# Natas12  
![Level 12 prob](https://user-images.githubusercontent.com/31714690/167221983-b23bd7e4-21b3-489e-858d-127ff8f11daa.png)


-The problem: File upload screen

-The Solution:

![Level 12 source code](https://user-images.githubusercontent.com/31714690/167222006-9c3ee466-5c39-454a-abee-a3ee8fb77d8c.png)

![Level 12 cod](https://user-images.githubusercontent.com/31714690/167222014-62639519-8b5a-4ea2-a0fe-95c0d06b2c96.png)

![Level 12 answer](https://user-images.githubusercontent.com/31714690/167222022-6527a3f8-5819-496d-8860-09f013b0f1bd.png)

  
# Natas13  


-The problem:

-The Solution:
  
# Natas14  
![Level 14 prob](https://user-images.githubusercontent.com/31714690/167222253-959301b3-ed11-4574-9e00-e35bfe68b1a1.png)


-The problem:

-The Solution:

![Level SQL injectin](https://user-images.githubusercontent.com/31714690/167222265-39fd38e6-46f1-4995-ad4e-382fcc7cfc8a.png)

![Level 14 answer](https://user-images.githubusercontent.com/31714690/167222276-c22989d2-73f6-46bb-b21e-fb53d86cbb3f.png)

  
# Natas15  
![Level 15 prob](https://user-images.githubusercontent.com/31714690/167222351-33ea8c18-4f33-490a-947d-8ccabac3ece8.png)


-The problem:

-The Solution:

![Level 15 dir](https://user-images.githubusercontent.com/31714690/167222365-6f2050cd-479c-4c50-8039-be31b9a1f916.png)

![Level 15 dirbuster](https://user-images.githubusercontent.com/31714690/167222373-04ff8af1-6069-4b70-af5f-89d3cdaa3766.png)

![Level 15 answer](https://user-images.githubusercontent.com/31714690/167222378-7294c48f-6fec-4aa5-b772-122171f1cf1d.png)

  
# Natas16  

![Level 16 prob](https://user-images.githubusercontent.com/31714690/167222439-d9e7c58a-cde7-41cb-984e-cc3cff39a1e7.png)

-The problem:

-The Solution: Here we used command injection in the search field. We used $() as command separators. Injected $(grep -E ^x.* /etc/natas_webpass/natas17) to determine if the password starts with letter X. Created a python script to solve password. 

![Level 16 php](https://user-images.githubusercontent.com/31714690/167222451-06b7e7da-814c-48b5-a2bb-a9d86fea1570.png)


![Level 16 script](https://user-images.githubusercontent.com/31714690/167222461-e74c96af-6db1-478e-a13b-527c9cf24029.png)


![Level 16 answer](https://user-images.githubusercontent.com/31714690/167222491-dff7467e-ebdb-4bcb-ad36-7709b5248104.png)

# Natas17  
![Level 17 prob](https://user-images.githubusercontent.com/31714690/167222662-2e0bce6a-6417-4532-a33d-998b9f7a9b3c.png)

![Level 17 php](https://user-images.githubusercontent.com/31714690/167222710-f6224544-979f-43cc-b89b-8d0c64193d52.png)

-The problem:

-The Solution: This is similar to the previous question, but had to use the SLEEP statement to determine if injection was TRUE or FALSE. Modified Python script to append the SLEEP statement.

![Level 17 script](https://user-images.githubusercontent.com/31714690/167222721-5c471f9e-5769-44d7-953b-2cdcc0bc2bf6.png)

![Level 17 answer](https://user-images.githubusercontent.com/31714690/167222726-5e3dace6-1775-41ed-9d45-bd730ba66541.png)

# Natas18  
![Level 18 prob](https://user-images.githubusercontent.com/31714690/167222815-62c946e4-066f-46b0-901a-dbe8d4755f01.png)


![Level 18 php](https://user-images.githubusercontent.com/31714690/167222882-5d49c618-566a-46a6-a9f4-aa41f1e53fc8.png)

-The problem: Login with an admin account

-The Solution: Brute forced the PHPSESSID, which is a value between 0-640. We created a Python script to automate the brute force.

![Level 18 script](https://user-images.githubusercontent.com/31714690/167222888-2c533208-284d-46b6-a51e-88de3452af5f.png)

![Level 18 answer](https://user-images.githubusercontent.com/31714690/167222897-5a4067f2-f425-4a8a-a120-d7c10e2d2a78.png)
  
# Natas19  
![Level 19 prob](https://user-images.githubusercontent.com/31714690/167223006-36b1016f-ce80-4c67-a652-577ae86ed8b2.png)

![Level 19 php](https://user-images.githubusercontent.com/31714690/167223074-94412fb3-6298-4a2a-9753-44097e29f554.png)

-The problem: Login with an admin account

-The Solution: Here we had to decode the cookie value which was in ASCII, slightly modified the Python code from Natas19 to match the cookie format on this problem.

![Level 19 script](https://user-images.githubusercontent.com/31714690/167223061-ac51b8ed-7702-4363-8815-840620af4e3b.png)

![Level 19 answer](https://user-images.githubusercontent.com/31714690/167223066-14e394eb-92bc-4619-a5d0-a1cfbd1cc11d.png)

  
# Natas20  
![Level 20 prob](https://user-images.githubusercontent.com/31714690/167223156-d9730296-55b8-489f-a5f3-b8053764822b.png)


-The problem: Presented with a empty field waiting for 'Your Name' input


![Level 20 php](https://user-images.githubusercontent.com/31714690/167223286-0ea95e9f-31b0-47b7-afce-b2fd26d7a4e0.png)

-The Solution: On this challenge, we exploited a vulnerability on the debug function for this website. We inserted a key/value pair of admin:1 to have the page 
return the answer.

![Level 20 path](https://user-images.githubusercontent.com/31714690/167223255-813658c0-2a7c-4ad8-a696-cf8f75c65e03.png)

![Level 20 answer](https://user-images.githubusercontent.com/31714690/167223272-8e90e765-6c95-4746-9e18-3fafb3830076.png)


