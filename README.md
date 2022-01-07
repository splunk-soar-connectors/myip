[comment]: # "Auto-generated SOAR connector documentation"
# Myip

Publisher: Splunk  
Connector Version: 2\.0\.4  
Product Vendor: Myip\.ms  
Product Name: Myip\.ms  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 4\.9\.39220  

This app integrates with the Myip\.ms service to implement investigative actions

### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a Myip\.ms asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**base\_url** |  required  | string | API Base URL
**api\_id** |  required  | string | API ID
**api\_key** |  required  | password | API Key

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity  
[whois domain](#action-whois-domain) - Execute whois lookup on the given domain  
[whois ip](#action-whois-ip) - Execute whois lookup on the given IP address  

## action: 'test connectivity'
Validate the asset configuration for connectivity

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'whois domain'
Execute whois lookup on the given domain

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**domain** |  required  | Domain to query | string |  `domain`  `url` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.domain | string |  `domain`  `url` 
action\_result\.data\.\*\.dns\.\*\.countryID | string | 
action\_result\.data\.\*\.dns\.\*\.countryIcon | string |  `url` 
action\_result\.data\.\*\.dns\.\*\.countryName | string | 
action\_result\.data\.\*\.dns\.\*\.ip\_address | string |  `ip`  `ipv6` 
action\_result\.data\.\*\.dns\.\*\.nameserver | string | 
action\_result\.data\.\*\.dns\.\*\.sites | string | 
action\_result\.data\.\*\.dns\.\*\.topSites | string | 
action\_result\.data\.\*\.error\_desc | string | 
action\_result\.data\.\*\.ip\_address | string |  `ip`  `ipv6` 
action\_result\.data\.\*\.ip\_change\_history\.\*\.date\_when\_found\_that\_website\_changed\_ip | string | 
action\_result\.data\.\*\.ip\_change\_history\.\*\.date\_when\_website\_was\_using\_ip | string | 
action\_result\.data\.\*\.ip\_change\_history\.\*\.host | string |  `ip`  `ipv6` 
action\_result\.data\.\*\.ip\_change\_history\.\*\.ip\_address | string |  `ip`  `ipv6` 
action\_result\.data\.\*\.ipv6\_address | string | 
action\_result\.data\.\*\.location\.countryID | string | 
action\_result\.data\.\*\.location\.countryIcon | string |  `url` 
action\_result\.data\.\*\.location\.countryName | string | 
action\_result\.data\.\*\.owners\.owner\.address | string | 
action\_result\.data\.\*\.owners\.owner\.cidr | string | 
action\_result\.data\.\*\.owners\.owner\.countryID | string | 
action\_result\.data\.\*\.owners\.owner\.countryIcon | string |  `url` 
action\_result\.data\.\*\.owners\.owner\.countryName | string | 
action\_result\.data\.\*\.owners\.owner\.link | string |  `url` 
action\_result\.data\.\*\.owners\.owner\.logo | string |  `url` 
action\_result\.data\.\*\.owners\.owner\.ownerName | string | 
action\_result\.data\.\*\.owners\.owner\.phone | string | 
action\_result\.data\.\*\.owners\.owner\.provider | string | 
action\_result\.data\.\*\.owners\.owner\.range | string | 
action\_result\.data\.\*\.owners\.owner\.rangeSize | string | 
action\_result\.data\.\*\.owners\.owner\.screenshot | string |  `url` 
action\_result\.data\.\*\.owners\.owner\.sites | string | 
action\_result\.data\.\*\.owners\.owner\.topSites | string | 
action\_result\.data\.\*\.owners\.owner\.website | string | 
action\_result\.data\.\*\.popularity\.image | string |  `url` 
action\_result\.data\.\*\.popularity\.rank | string | 
action\_result\.data\.\*\.popularity\.rankWebsite | string | 
action\_result\.data\.\*\.popularity\.text | string | 
action\_result\.data\.\*\.popularity\.visitors | string | 
action\_result\.data\.\*\.query | string | 
action\_result\.data\.\*\.reverse\_dns\.host | string | 
action\_result\.data\.\*\.reverse\_dns\.topHost\.countryID | string | 
action\_result\.data\.\*\.reverse\_dns\.topHost\.countryName | string | 
action\_result\.data\.\*\.reverse\_dns\.topHost\.ip\_address | string | 
action\_result\.data\.\*\.reverse\_dns\.topHost\.sites | string | 
action\_result\.data\.\*\.reverse\_dns\.topHost\.text | string | 
action\_result\.data\.\*\.reverse\_dns\.topHost\.topHostName | string |  `host name` 
action\_result\.data\.\*\.status | string | 
action\_result\.data\.\*\.website | string | 
action\_result\.summary\.found | boolean | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'whois ip'
Execute whois lookup on the given IP address

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip** |  required  | IP to query | string |  `ip`  `ipv6` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.ip | string |  `ip`  `ipv6` 
action\_result\.data\.\*\.browsers\_on\_ip\.\*\.browser | string | 
action\_result\.data\.\*\.browsers\_on\_ip\.\*\.browserIcon | string |  `url` 
action\_result\.data\.\*\.crawlerbot\_use\_ip | string | 
action\_result\.data\.\*\.dns\_on\_ip\.\*\.nameserver | string |  `ip`  `ipv6` 
action\_result\.data\.\*\.dns\_on\_ip\.\*\.sites | string | 
action\_result\.data\.\*\.dns\_on\_ip\.\*\.topSites | string | 
action\_result\.data\.\*\.ip\_address | string |  `ip`  `ipv6` 
action\_result\.data\.\*\.ip\_blacklist\.blacklist | string | 
action\_result\.data\.\*\.ip\_blacklist\.latest\_site\_visit\_date | string | 
action\_result\.data\.\*\.ip\_blacklist\.latest\_thread | string | 
action\_result\.data\.\*\.location\.countryID | string | 
action\_result\.data\.\*\.location\.countryIcon | string |  `url` 
action\_result\.data\.\*\.location\.countryName | string | 
action\_result\.data\.\*\.not\_working\_websites\_on\_ip\.\*\.date\_when\_website\_was\_using\_ip | string | 
action\_result\.data\.\*\.not\_working\_websites\_on\_ip\.\*\.image | string |  `url` 
action\_result\.data\.\*\.not\_working\_websites\_on\_ip\.\*\.rank | string | 
action\_result\.data\.\*\.not\_working\_websites\_on\_ip\.\*\.text | string | 
action\_result\.data\.\*\.not\_working\_websites\_on\_ip\.\*\.visitors | numeric | 
action\_result\.data\.\*\.not\_working\_websites\_on\_ip\.\*\.website | string | 
action\_result\.data\.\*\.os\_on\_ip\.\*\.os | string | 
action\_result\.data\.\*\.os\_on\_ip\.\*\.osIcon | string |  `url` 
action\_result\.data\.\*\.owners\.owner\.address | string | 
action\_result\.data\.\*\.owners\.owner\.cidr | string | 
action\_result\.data\.\*\.owners\.owner\.countryID | string | 
action\_result\.data\.\*\.owners\.owner\.countryIcon | string |  `url` 
action\_result\.data\.\*\.owners\.owner\.countryName | string | 
action\_result\.data\.\*\.owners\.owner\.link | string |  `url` 
action\_result\.data\.\*\.owners\.owner\.logo | string |  `url` 
action\_result\.data\.\*\.owners\.owner\.ownerName | string | 
action\_result\.data\.\*\.owners\.owner\.phone | string | 
action\_result\.data\.\*\.owners\.owner\.provider | string | 
action\_result\.data\.\*\.owners\.owner\.range | string | 
action\_result\.data\.\*\.owners\.owner\.rangeSize | string | 
action\_result\.data\.\*\.owners\.owner\.screenshot | string |  `url` 
action\_result\.data\.\*\.owners\.owner\.sites | string | 
action\_result\.data\.\*\.owners\.owner\.topSites | string | 
action\_result\.data\.\*\.owners\.owner\.website | string | 
action\_result\.data\.\*\.owners\.parent\_owner\.address | string | 
action\_result\.data\.\*\.owners\.parent\_owner\.cidr | string | 
action\_result\.data\.\*\.owners\.parent\_owner\.countryID | string | 
action\_result\.data\.\*\.owners\.parent\_owner\.countryIcon | string |  `url` 
action\_result\.data\.\*\.owners\.parent\_owner\.countryName | string | 
action\_result\.data\.\*\.owners\.parent\_owner\.link | string |  `url` 
action\_result\.data\.\*\.owners\.parent\_owner\.logo | string |  `url` 
action\_result\.data\.\*\.owners\.parent\_owner\.ownerName | string | 
action\_result\.data\.\*\.owners\.parent\_owner\.phone | string | 
action\_result\.data\.\*\.owners\.parent\_owner\.provider | string | 
action\_result\.data\.\*\.owners\.parent\_owner\.range | string | 
action\_result\.data\.\*\.owners\.parent\_owner\.rangeSize | string | 
action\_result\.data\.\*\.owners\.parent\_owner\.screenshot | string |  `url` 
action\_result\.data\.\*\.owners\.parent\_owner\.sites | string | 
action\_result\.data\.\*\.owners\.parent\_owner\.topSites | string | 
action\_result\.data\.\*\.owners\.parent\_owner\.website | string | 
action\_result\.data\.\*\.query | string |  `ip`  `ipv6` 
action\_result\.data\.\*\.statistics\.total\_browsers\_on\_ip | numeric | 
action\_result\.data\.\*\.statistics\.total\_dns\_on\_ip | numeric | 
action\_result\.data\.\*\.statistics\.total\_not\_working\_websites\_on\_ip | string | 
action\_result\.data\.\*\.statistics\.total\_os\_on\_ip | numeric | 
action\_result\.data\.\*\.statistics\.total\_useragents\_on\_ip | numeric | 
action\_result\.data\.\*\.statistics\.total\_websites\_on\_ip\_before | string | 
action\_result\.data\.\*\.statistics\.total\_websites\_on\_ip\_now | string | 
action\_result\.data\.\*\.status | string | 
action\_result\.data\.\*\.useragents\_on\_ip\.\*\.browser | string | 
action\_result\.data\.\*\.useragents\_on\_ip\.\*\.browserIcon | string |  `url` 
action\_result\.data\.\*\.useragents\_on\_ip\.\*\.latest\_site\_visit\_date | string | 
action\_result\.data\.\*\.useragents\_on\_ip\.\*\.os | string | 
action\_result\.data\.\*\.useragents\_on\_ip\.\*\.osIcon | string |  `url` 
action\_result\.data\.\*\.useragents\_on\_ip\.\*\.useragent | string | 
action\_result\.data\.\*\.websites\_on\_ip\_before\.\*\.date\_when\_found\_that\_website\_changed\_ip | string | 
action\_result\.data\.\*\.websites\_on\_ip\_before\.\*\.date\_when\_website\_was\_using\_ip | string | 
action\_result\.data\.\*\.websites\_on\_ip\_before\.\*\.image | string |  `url` 
action\_result\.data\.\*\.websites\_on\_ip\_before\.\*\.rank | string | 
action\_result\.data\.\*\.websites\_on\_ip\_before\.\*\.text | string | 
action\_result\.data\.\*\.websites\_on\_ip\_before\.\*\.visitors | numeric | 
action\_result\.data\.\*\.websites\_on\_ip\_before\.\*\.website | string | 
action\_result\.data\.\*\.websites\_on\_ip\_now\.\*\.image | string |  `url` 
action\_result\.data\.\*\.websites\_on\_ip\_now\.\*\.rank | string | 
action\_result\.data\.\*\.websites\_on\_ip\_now\.\*\.text | string | 
action\_result\.data\.\*\.websites\_on\_ip\_now\.\*\.visitors | string | 
action\_result\.data\.\*\.websites\_on\_ip\_now\.\*\.website | string | 
action\_result\.summary\.found | boolean | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 