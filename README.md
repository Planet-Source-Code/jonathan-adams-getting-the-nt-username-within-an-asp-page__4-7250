<div align="center">

## Getting the NT Username within an ASP Page


</div>

### Description

Every wanted to get the currently authenticated NT user name from your intranet/internet site when you have authenication turned on.  The code below removes the domain name and leaves you with the NT User name.
 
### More Info
 
Returns a string variable containing the NT User name


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Jonathan Adams](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/jonathan-adams.md)
**Level**          |Beginner
**User Rating**    |3.8 (19 globes from 5 users)
**Compatibility**  |ASP \(Active Server Pages\)
**Category**       |[Security](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/security__4-14.md)
**World**          |[ASP / VbScript](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/asp-vbscript.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/jonathan-adams-getting-the-nt-username-within-an-asp-page__4-7250/archive/master.zip)

### API Declarations

(c) Illuminaries Ltd 2002 . All rights reserved.


### Source Code

```
Public Function split_logonname()
'-------------------------------------------------
' (c) Illuminaries Ltd 2002 . All rights reserved.
'-------------------------------------------------'	Written By : Jonathan Adams (MCP)
'	web address : www.illuminaries.co.uk
'-------------------------------------------------' Change the code as you please but please
'leave the copyright information
'-------------------------------------------------
' Description :
'-------------------------------------------------' The NT Auth. logon name contains the domain
'name along with the logon name. This routine
' removes the domain name and returns the Logon name only
'-------------------------------------------------
Dim strUsername
Dim l_splitpoint
strUsername=Request.ServerVariables("LOGON_USER")
l_splitpoint=instr(strUserName,"\")
	if l_splitpoint>0 then
		split_logonname=right(strUsername,len(strUsername) - (l_splitpoint))
	else
		l_splitpoint=instr(strUserName,"/")
		if l_splitpoint>0 then
			split_logonname=right(strUsername,len(strUsername) - (l_splitpoint))
		else
			split_logonname=strUsername
		end if
	end if
End Function
```

