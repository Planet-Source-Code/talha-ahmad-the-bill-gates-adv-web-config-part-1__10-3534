<div align="center">

## Adv Web\.Config Part 1


</div>

### Description

This article is A-Z Web.Config for Forms Authentication. Good for Beginners.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Talha Ahmad, the Bill Gates](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/talha-ahmad-the-bill-gates.md)
**Level**          |Beginner
**User Rating**    |4.2 (21 globes from 5 users)
**Compatibility**  |C\#, VB\.NET, ASP\.NET, C\+\+\.NET
**Category**       |[Miscellaneous](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/miscellaneous__10-1.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/talha-ahmad-the-bill-gates-adv-web-config-part-1__10-3534/archive/master.zip)





### Source Code

<b>
Advanced Web.Config for Authentication
</b>
<br>
http://www.talha.co.uk
<br><br><br>
Well, After receiving so many emails asking about Web.Config, I have decided to write an article on "Web.Config for Forms
Authentication".
<br><br>
First of all, there are three types of Authentication methods:
<br><br>
	Windows Authentication<br>
	Forms Authentication<br>
	Passport Authentication<br>
<br><br><br>
Since this article is about Web.Config, I am not going to explain what the above three do, how and why? So Let's start
writing a Web.Config for Forms Authentication.
<br><br>
In my Web.Config file, I will find my Authentication node and change it to the following:
<br><br><b>
&lt;authentication mode="Forms"&gt;<br>
	&lt;forms name=".ASPXAUTH" protection="All" timeout="60" loginUrl="default.aspx" /&gt;<br>
&lt;/authentication&gt;<br></b>
<br><br>
and then I will find the Authorization node and change it as follows:<br><br>
<b>
&lt;authorization&gt;<br>
	&lt;deny users="?" /&gt;<br>
&lt;/authorization&gt;<br>
</b><br><br>
If the user wants to see a restricted access, it will take him to the default.aspx page. You can change it to Login.aspx or
anything. Now, another import thing to know is that not all the pages are restricted in a web application, are they? So you
want to tell the program to let the users view the pages which are not. So between your
<b><br><br>
&lt;/system.web&gt; and &lt;/configuration&gt; </b> in Web.Config file, add the following lines:
<br><br>
<b>&lt;location path="default.aspx"&gt;<br>
	&lt;system.web&gt;<br>
		&lt;authorization&gt;<br>
			&lt;allow users="?" /&gt;<br>
		&lt;/authorization&gt;<br>
	&lt;/system.web&gt;<br>
	&lt;/location&gt;<br>
<br><br>
&lt;location path="login.aspx"&gt;<br>
	&lt;system.web&gt;<br>
		&lt;authorization&gt;<br>
			&lt;allow users="?" /&gt;<br>
		&lt;/authorization&gt;<br>
	&lt;/system.web&gt;<br>
&lt;/location&gt;<br>
</b><br><br>
Now it will let the users view default.aspx and login.aspx. If you want to add more pages, copy and paste the above lines and
change the name of the pages.
<br><br>
My next article will be on Forms Authentication and come with Samples. So please vote and motivate me to take some time out
and write it for you. Visit my web site for articles, my online projects, E-PDF Creator, E-Chat, E-Messenger and E-Charts. A
good site for newbies. http://www.talha.co.uk
<br><br><br>

