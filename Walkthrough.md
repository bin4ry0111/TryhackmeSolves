#JOYSTICK CTF

#Machines ip: 10.10.241.107
	
	cmd: nmap -A -v -p- <ip> 
	open ports:
		21
		80
		22

When we go to the http://ip and check the page source code,we can see there is a message.
	from there we get 
	
		USERNAME - steve
		Weak password ftp+ssh
		ftp not working
		message to Zach

So we can use hydra to bruteforce the credentials.

	hydra -l steve -P rockyou.txt ssh://10.10.241.107

#Results: 

	we got the credentials [steve:changeme]

Now lets ssh the ip..and see whats there
	
	ok..we got our first flag in user.txt 
		ans 1: [flag{is_only_gaem}]
		
So,when go to home we see there is another user named notch.

	In there,we get the final flag root.txt
		ans 2: [flag{poorly_configured_permissions}]


[End of the Game]

