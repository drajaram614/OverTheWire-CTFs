# Bandit CTFs

## What I Learned:
The Bandit CTF provided hands-on experience with essential Linux commands, scripting, networking, and privilege escalation techniques, all of which are fundamental to cybersecurity. Throughout the challenges, I developed proficiency in file operations, such as searching, reading, and manipulating data securely using `ssh`, `cat`, `find`, and other commands. I learned how to handle encoded and compressed data using utilities like `base64`, `gzip`, and `xxd`, which are vital for tasks like malware analysis and decoding obfuscated data. I also gained experience with shell scripting to automate repetitive tasks, a critical skill for optimizing security workflows.

In networking, I utilized tools like `nc` and `nmap` to identify open ports and services, and I applied SSL/TLS protocols for secure communications. Privilege escalation techniques, such as exploiting `setuid` binaries, provided insight into the vulnerabilities that attackers target in real-world environments. Additionally, working with Git repositories helped reinforce secure software development practices. I also learned to bypass restricted shells, further developing my ability to think critically and exploit weaknesses in constrained environments.

Overall, the CTF honed my command-line proficiency, automation skills, and understanding of networking, privilege escalation, and file security—key areas in penetration testing, incident response, and system hardening.

## General Commands:
- **`ssh -p`**: Initiates a secure shell connection to a remote server on a specific port. Used to connect to the Bandit challenges.
- **`mkdir`**: Creates a directory, useful for organizing files or scripts.

## File Manipulation Commands:
- **`cat ./-`**: Displays the contents of a file named `-`. The `./` ensures the file is in the current directory.
- **`cat spaces\ in\ this\ filename`**: Reads and outputs the contents of a file with spaces in its name. The backslashes escape the spaces.

## Searching and Filtering Commands:
- **`find . -type f | xargs file`**: Searches for files and passes them to the `file` command to identify their type.
- **`find . -type f -size 1033c ! -executable`**: Finds files of a specific size (1033 bytes) that are not executable.
- **`find / -type f -user bandit7 -group bandit6 -size 33c`**: Locates files owned by a specific user and group.
- **`grep millionth data.txt`**: Searches for the string "millionth" within `data.txt`.
- **`cat data.txt | sort | uniq -u`**: Finds the unique line in `data.txt`. The command sorts the lines and filters out duplicates.
- **`strings data.txt | grep ===`**: Extracts human-readable strings from binary data and filters for lines containing `===`.

## Encoding and Decoding Commands:
- **`strings data.txt | base64 -d`**: Decodes `base64`-encoded data.
- **`cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'`**: Decodes ROT13-encrypted data, shifting letters by 13 positions.

## Compression and Decompression:
- **`mv data data.gz; gzip -d data.gz`**: Renames a file and decompresses it using `gzip`.

## SSH and Authentication:
- **`ssh -i sshkey.private -p 2220 bandit14@localhost`**: Uses a private SSH key to log into the next level of the Bandit challenge.

## Networking Commands:
- **`nc localhost 30000`**: Opens a network connection to port 30000 on localhost to retrieve data.
- **`ncat --ssl localhost 30001`**: Similar to `nc`, but uses SSL/TLS encryption for secure communication.
- **`nmap localhost -p 31000-32000`**: Scans the localhost for open ports within a specified range.

## File Comparison:
- **`diff passwords.old passwords.new`**: Compares two files and displays the differences.

## Escaping Restricted Shells:
- **`ssh -t bandit18@bandit.labs.overthewire.org -p 2220 /bin/sh`**: Forces SSH to use `/bin/sh` to avoid restrictions set by `.bashrc`.

## SUID Binaries:
- **`bandit20-do ./bandit20-do cat /etc/bandit_pass/bandit20`**: Uses a `setuid` binary to execute privileged commands.

## Daemon Interaction and Scripting:
- **`nc -l -p 1234`**: Listens for connections on port 1234 using `nc`.
- **`brute.sh`**: A brute-force script that tries all possible 4-digit combinations to break into a system.

## Git Commands:
- **`git clone`**: Clones a remote Git repository.
- **`git branch -r`**: Lists all remote branches in a Git repository.
- **`git log`**: Displays the commit history.
- **`git show`**: Shows the changes made in a specific commit.
- **`git checkout`**: Switches branches or restores files.
- **`git tag`**: Lists and manages Git tags.

## Shell Manipulation:
- **`:e /etc/bandit_pass/bandit26`**: Opens a file using the vim editor from within the `more` command to escape a restricted environment.
- **`:set shell=/bin/bash; :shell`**: Sets the shell to `/bin/bash` and starts it, escaping from a restricted shell environment.

## Escaping the UPPERCASE Shell:
- **`export SHELL=/bin/bash; $SHELL`**: Sets the environment variable `SHELL` to `/bin/bash` and starts a new bash session to escape from the restricted shell.

## Conclusion:
These commands cover a variety of tasks, from networking and file manipulation to escaping restricted environments and using Git. The commands were applied strategically in CTF challenges to solve problems by navigating the system, working with files, and interacting with services.


## Skills

### Linux Proficiency
Developed deep command-line proficiency, which is foundational for cybersecurity professionals. Linux underpins many security tools and servers, making these skills essential for monitoring, defending, and attacking systems.

### Automation with Scripting
Utilized bash scripts to automate repetitive tasks, improving efficiency in incident response, vulnerability scanning, and system administration. Automation is vital for scaling security operations and reducing manual effort in complex tasks.

### Privilege Escalation
Gained insight into how improper file permissions and misconfigured binaries can be exploited for privilege escalation. Understanding this is critical for both ethical hacking (offensive roles) and ensuring proper hardening of systems (defensive roles).

### Networking Knowledge
Explored networking fundamentals such as open port identification, service exploitation, and secure communications. These skills are crucial for vulnerability assessments, penetration testing, and incident response.

### File and Data Manipulation
Acquired the ability to search, extract, and decode hidden or obfuscated data. These techniques are key in reverse engineering malware, analyzing data breaches, and conducting digital forensics.

### Critical Thinking and Problem Solving
Developed an analytical mindset by breaking down complex problems into solvable steps. This is essential for diagnosing issues, identifying security vulnerabilities, and implementing effective mitigations in real-world IT environments.

### Version Control with Git
Reinforced secure software development practices by working with Git for version control, managing code changes, and collaborating in a team setting—an indispensable skill in modern DevSecOps and secure coding environments.