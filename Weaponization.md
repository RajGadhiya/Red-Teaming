# Red Teaming Squad : Weaponization

Weaponization consists of techniques that result in adversary-controlled code running on a local or remote system. Techniques that run malicious code are often paired with techniques from all other tactics to achieve broader goals, like exploring a network or stealing data. For example, an adversary might use a remote access tool to run a PowerShell script that does Remote System Discovery. Most of these techniques do not require a Tool but just access and Native Tools from the Windows Machine itself one of the reasons we want to use.


## Unicorn

Magic Unicorn is a simple tool for using a PowerShell downgrade attack and inject shellcode straight into memory.


### Installation

You can install "Unicorn" using following command:

```
git clone https://github.com/trustedsec/unicorn
```

<kbd>![](Weaponization/1.png)</kbd>

### Usage

Usage is simple, just run Magic Unicorn (ensure Metasploit is installed if using Metasploit methods and in the right path) and magic unicorn will automatically generate a powershell command that you need to simply cut and paste the powershell code into a command line window or through a payload delivery system. Unicorn supports your own shellcode, cobalt strike, and Metasploit.

Here we are using windows/meterpreter/reverse_tcp payload to get the reverse shell because our target system has Windows Operating System.

<kbd>![](Weaponization/2.png)</kbd>

Now this will give us two files. One is a text file named “powershell_attack.txt” which has the PowerShell code that will be run in the victim’s machine using social engineering and the other is “unicorn.rc” which is a custom Metasploit file that will automatically set all the parameters and start a listener.

<kbd>![](Weaponization/3.png)</kbd>

We need to run the Metasploit “unicorn.rc” file using ```msfconsole -r unicorn.rc``` command which will setup our listener.

<kbd>![](Weaponization/4.png)</kbd>

Now execute the powershell command through powershell using any social engineering technoque.

<kbd>![](Weaponization/5.png)</kbd>

Once the PowerShell code was executed in the victim’s powershell command promt, you will see a meterpreter session of your victim. 

<kbd>![](Weaponization/6.png)</kbd>

For more use cases, you can use ```python unicorn.py --help``` command or you can visit this [URL](https://github.com/trustedsec/unicorn).