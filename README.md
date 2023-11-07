# Test a user's Online Voice Routing Policy for Teams Direct Routing

Using this script you can test a user's assigned Online Voice Routing Policy - this policy is used to decide how to route Direct Routing calls. 
Simply provide a dialed number and a user to see what Voice Routes would be used and in what order.

## Usage

> Make Sure you have **v4.9.3+** Microsoft Teams PowerShell module installed.
> 
```sh    
    .\Test-CSOnlineUserVoiceRouting.ps1 -DialedNumber 0420123456 -User user@domain.com
   
    This will list any Voice Routes (in priority order) for user@domain.com calling 0420123456

    Getting Effective Tenant Dial Plan for user1@lab.testit.vc and translating number...
    0420123456 translated to +61420123456

    Using rule:
	Description = Mobile number normalization for Australia
	Pattern=^0(([45]\d{8}))$
	Translation=+61$1
	Name=AU-Mobile
	IsInternalExtension=False)

    Getting assigned Online Voice Routing Policy for user1@lab.testit.vc...
    Online Voice Routing Policy assigned to user1@lab.testit.vc is: 'AU-International-Calling'

    Finding the first PSTN Usage with a Voice Route that matches +61420123456...
    First Matching PSTN Usage: 'AU-Mobile'
    
    Found 1 Voice Route(s) with matching pattern in PSTN Usage 'AU-Mobile', listing in priority order...

    Name      NumberPattern     PSTNUsage OnlinePstnGatewayList Priority
    ----      -------------     --------- --------------------- --------
    AU-Mobile ^\+61([45]\d{8})$ AU-Mobile {SBC.domain.com}        2
    
```

**This script is provided ‘as-is’, Use of this script is at your own risk and always check code before running it.**
