<img width="931" height="545" alt="ping-cmd-picoCTF challenge" src="https://github.com/user-attachments/assets/71ffb40d-3eed-4ddc-92a5-442083109a69" />


# picoCTF - ping-cmd

## Challenge Description
Can you make the server reveal its secrets? The service appears to allow users to ping a DNS server, but user input may not be properly sanitized.

Connection provided:
`nc mysterious-sea.picoctf.net 50578`

## Objective
The goal of this challenge was to identify and exploit a command injection vulnerability in the ping functionality to execute arbitrary system commands and retrieve the hidden flag.

## Tools Used
- Netcat (nc)
- Linux terminal

## Steps

### 1. Initial Interaction
After connecting to the service using netcat, I was prompted to enter an IP address to ping. The application returned output from the system ping command.

### 2. Testing Input for Injection
I tested whether additional commands could be executed by appending a command separator (`;`) to the input.

I entered: 8.8.8.8; ls

This worked, indicating the input was being directly passed to a system shell without sanitization.

### 3. Directory Enumeration
Using command injection, I listed files in the current directory and discovered a file named:

### 4. Retrieving the Flag
I used command injection again to read the contents of the file: 8.8.8.8; cat flag.txt

## Flag
picoCTF{p1nG_c0mm@nd_3xpL0it_suc33essFuL_252214ae}

## Key Takeaways
- Identified a command injection vulnerability in a network service
- Learned how command separators (`;`) can be used for injection
- Practiced basic remote enumeration using netcat
