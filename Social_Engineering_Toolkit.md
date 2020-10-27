# Red Teaming Squad


## Macro

### What is Macro?

Whenever we work with an excel or a word file and we want a certain repetitive task that we wish just get automated without our intervention at that time we can use macro. Macros are similar to Visual Basic Scripts that can be crafted and shared and it works in the background without any knowledge of the user. We can use malicious macro to gain access of victim's machine. Attacker will create a word or excel file then attacker opens the macro editor to generate a script which can generate the session from victim'e machine to attacker's machine. 


### Generate macro payloads using Empire

You can install Empire tool from github or by executing ```git clone https://github.com/EmpireProject/Empire``` command. Navigate to ```Empire``` directory and execute ```./empire``` command. Now start a listener using ```uselistener http``` then check that your listener is active or not using ```listeners``` command.

<kbd>![](Macro_Payloads/1.png)</kbd>
