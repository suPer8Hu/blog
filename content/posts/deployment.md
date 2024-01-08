---
title : 'Deployment'
date : 2024-01-07T15:59:42-05:00
draft : false
author : Hu
tags: ["UW-Madiosn", "CS544", "Linux Shell", "Deployment"]
categories: ["Courses"]
---

### **Deployment (Linux Shell)**  
To run the python file in bash or called Linux Shell, there are some basic linux commands you will need to get familiar with:  
```
mkdir data
```  
to create a new directory named data  
And you can check this with ```ls -l```  
```
drwxr-xr-x  2 changlinhu  staff  64 Jan  6 00:11 data
```  
the very first character "d" which stands for directory means data is not a file but a directory, and 'rwx' means read, write and excutable. "-" used to separate the different user groups, so the first group before the dash is the user, which following the group and everybody. 64 is the size of the directory, you can also use ```ls -lh``` to represent, where h stands for human-readable.  
```
drwxr-xr-x  2 changlinhu  staff    64B Jan  6 00:11 data
```  
Now, you can touch a file called test.txt: ```touch test.txt```  
```
-rw-r--r--  1 changlinhu  staff   0 Jan  6 00:22 test.txt
```  
you can see all the permission from the above.  
But if you want to change the mode permisson you can do: ```chmod a+w test.txt``` which means change mode all user with write permissions to the test.txt file. Then check you can see that change to write permissions:  
```
-rw-rw-rw-  1 changlinhu  staff   0 Jan  6 00:22 test.txt
```
Now what if we want to run a python program in shell, count.py: 
```
count = 0
with open("test.txt") as f:
	for line in f:
		count += 1
print(count)
```   
```python3 count.py``` to run the program in bash.  
However, when we run with ```./count.py```, it showing us that: ```zsh: permission denied: ./count.py```, so why this happens?  
We can check with the ```ls -l``` command and clearly see that count.py is not a excutable file right now:  
```
-rw-r--r--  1 changlinhu  staff  80 Jan  7 12:26 count.py
``` 
So we have to change the mode with ```chmod u+x count.py```, to set permission tp user with excutable to count.py file. Now we ```ls -l``` and found that:  
```
-rwxr--r--  1 changlinhu  staff  80 Jan  7 12:26 count.py
```
Then, we do ```./count.py``` to run the program but we got:  
```
./count.py: line 1: count: command not found
./count.py: line 2: syntax error near unexpected token `('
./count.py: line 2: `with open("test.txt") as f:'
```
For this situation, system is trying to run this as a shell script but python program is not. But we can solve this with ```Shebang line```: ```#!```  
So basically, we need to ```which python3``` first and get the path of it, for example: ```/Library/Frameworks/Python.framework/Versions/3.9/bin/python3```  
After that we can modify our count.py python file, just add this at the very beginning of the count.py:  
```
#! /Library/Frameworks/Python.framework/Versions/3.9/bin/python3
```
Now, we can run the program like this```./count.py```  

总结一下：
- 在Unix和Linux系统中，#!加上一个解释器路径的行用于指定执行脚本的解释器。
- 当这行被添加到Python脚本的顶部时，它使得脚本可以作为可执行文件直接运行，而不需要显式调用Python解释器（例如通过python3 count.py的方式来运行）。  

But why can't we run with the command ```count.py``` directly?  
```
zsh: command not found: count.py
```  
At this time, you will need to ```echo $PATH``` and get the path ```/Users/changlinhu/.nvm/versions/node/v16.17.0/bin:/Library/Frameworks/Python.framework/Versions/3.9/bin:/usr/local/bin:/System/Cryptexes/App/usr/bin:/usr/bin:/bin:/usr/sbin:/sbin:/var/run/com.apple.security.cryptexd/codex.system/bootstrap/usr/local/bin:/var/run/com.apple.security.cryptexd/codex.system/bootstrap/usr/bin:/var/run/com.apple.security.cryptexd/codex.system/bootstrap/usr/appleinternal/bin:/opt/X11/bin:/Library/Apple/usr/bin:/Applications/VMware Fusion.app/Contents/Public:~/.dotnet/tools:/Library/Frameworks/Mono.framework/Versions/Current/Commands:/opt/homebrew/bin/:/Applications/IntelliJ IDEA.app/Contents/bin```, in here this separated with ":", then you will have to:  
```
mv count.py /Users/changlinhu/.nvm/versions/node/v16.17.0/bin
```  
Eventually you can run it as ```count.py``` directly!  
We can also use ```which count.py``` to check the path of the count.py

