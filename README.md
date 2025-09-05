# Myip

Publisher: Splunk <br>
Connector Version: 2.0.6 <br>
Product Vendor: Myip.ms <br>
Product Name: Myip.ms <br>
Minimum Product Version: 4.9.39220

This app integrates with the Myip.ms service to implement investigative actions

### Configuration variables

This table lists the configuration variables required to operate Myip. These variables are specified when configuring a Myip.ms asset in Splunk SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**base_url** | required | string | API Base URL |
**api_id** | required | string | API ID |
**api_key** | required | password | API Key |

### Supported Actions

[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity <br>
[whois domain](#action-whois-domain) - Execute whois lookup on the given domain <br>
[whois ip](#action-whois-ip) - Execute whois lookup on the given IP address

## action: 'test connectivity'

Validate the asset configuration for connectivity

Type: **test** <br>
Read only: **True**

#### Action Parameters

No parameters are required for this action

#### Action Output

No Output

## action: 'whois domain'

Execute whois lookup on the given domain

Type: **investigate** <br>
Read only: **True**

#### Action Parameters

PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**domain** | required | Domain to query | string | `domain` `url` |

#### Action Output

DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.status | string | | failed success |
action_result.parameter.domain | string | `domain` `url` | google.com http://www.mydomaindoesnotexist.com/ |
action_result.data.\*.dns.\*.countryID | string | | USA |
action_result.data.\*.dns.\*.countryIcon | string | `url` | https://myip.ms/images/devices/16/flags/USA.png |
action_result.data.\*.dns.\*.countryName | string | | USA |
action_result.data.\*.dns.\*.ip_address | string | `ip` `ipv6` | 216.239.32.10 |
action_result.data.\*.dns.\*.nameserver | string | | ns1.google.com |
action_result.data.\*.dns.\*.sites | string | | 709 710 |
action_result.data.\*.dns.\*.topSites | string | | 229 |
action_result.data.\*.error_desc | string | | Invalid IP/Website |
action_result.data.\*.ip_address | string | `ip` `ipv6` | 172.217.13.238 |
action_result.data.\*.ip_change_history.\*.date_when_found_that_website_changed_ip | string | | 27 Dec 2017 |
action_result.data.\*.ip_change_history.\*.date_when_website_was_using_ip | string | | 27 Dec 2017 |
action_result.data.\*.ip_change_history.\*.host | string | `ip` `ipv6` | lga25s62-in-f14.1e100.net |
action_result.data.\*.ip_change_history.\*.ip_address | string | `ip` `ipv6` | 172.217.12.174 |
action_result.data.\*.ipv6_address | string | | 2607:f8b0:4004:809::200e |
action_result.data.\*.location.countryID | string | | USA |
action_result.data.\*.location.countryIcon | string | `url` | https://myip.ms/images/devices/16/flags/USA.png |
action_result.data.\*.location.countryName | string | | United States |
action_result.data.\*.owners.owner.address | string | | 1600 Amphitheatre Parkway, Mountain View, CA, 94043, US |
action_result.data.\*.owners.owner.cidr | string | | 172.217.0.0/16 |
action_result.data.\*.owners.owner.countryID | string | | USA |
action_result.data.\*.owners.owner.countryIcon | string | `url` | https://myip.ms/images/devices/16/flags/USA.png |
action_result.data.\*.owners.owner.countryName | string | | USA |
action_result.data.\*.owners.owner.link | string | `url` | https://myip.ms/view/ip_owners/617 |
action_result.data.\*.owners.owner.logo | string | `url` | https://myip.ms/docs/ip_owners/1/google_inc_logo.png |
action_result.data.\*.owners.owner.ownerName | string | | Google Inc |
action_result.data.\*.owners.owner.phone | string | | +1-650-253-0000 |
action_result.data.\*.owners.owner.provider | string | | |
action_result.data.\*.owners.owner.range | string | | 172.217.0.0 - 172.217.255.255 |
action_result.data.\*.owners.owner.rangeSize | string | | 65536 |
action_result.data.\*.owners.owner.screenshot | string | `url` | https://myip.ms/docs/ip_owners/1/google-inc.png |
action_result.data.\*.owners.owner.sites | string | | 130006 |
action_result.data.\*.owners.owner.topSites | string | | 1848 |
action_result.data.\*.owners.owner.website | string | | sites.google.com |
action_result.data.\*.popularity.image | string | `url` | https://myip.ms/images/popularity/rating10.png |
action_result.data.\*.popularity.rank | string | | 1 |
action_result.data.\*.popularity.rankWebsite | string | | google.com |
action_result.data.\*.popularity.text | string | | 655,000,000 visitors per day |
action_result.data.\*.popularity.visitors | string | | 655000000 |
action_result.data.\*.query | string | | google.com www.mydomaindoesnotexist.com |
action_result.data.\*.reverse_dns.host | string | | iad23s61-in-f4.1e100.net |
action_result.data.\*.reverse_dns.topHost.countryID | string | | |
action_result.data.\*.reverse_dns.topHost.countryName | string | | |
action_result.data.\*.reverse_dns.topHost.ip_address | string | | |
action_result.data.\*.reverse_dns.topHost.sites | string | | 44474 44470 |
action_result.data.\*.reverse_dns.topHost.text | string | | 44,474 sites use XXX.1e100.net as IP Reverse DNS 44,470 sites use XXX.1e100.net as IP Reverse DNS |
action_result.data.\*.reverse_dns.topHost.topHostName | string | `host name` | 1e100.net |
action_result.data.\*.status | string | | ok error |
action_result.data.\*.website | string | | google.com |
action_result.summary.found | boolean | | True False |
action_result.message | string | | Found: True Found: False |
summary.total_objects | numeric | | 2 1 |
summary.total_objects_successful | numeric | | 1 |

## action: 'whois ip'

Execute whois lookup on the given IP address

Type: **investigate** <br>
Read only: **True**

#### Action Parameters

PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip** | required | IP to query | string | `ip` `ipv6` |

#### Action Output

DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.status | string | | success failed |
action_result.parameter.ip | string | `ip` `ipv6` | 8.8.8.8 |
action_result.data.\*.browsers_on_ip.\*.browser | string | | Firefox 10 |
action_result.data.\*.browsers_on_ip.\*.browserIcon | string | `url` | https://myip.ms/images/browsers/0/6.png |
action_result.data.\*.crawlerbot_use_ip | string | | yes |
action_result.data.\*.dns_on_ip.\*.nameserver | string | `ip` `ipv6` | google-public-dns-a.google.com |
action_result.data.\*.dns_on_ip.\*.sites | string | | 50 |
action_result.data.\*.dns_on_ip.\*.topSites | string | | 3 |
action_result.data.\*.ip_address | string | `ip` `ipv6` | 8.8.8.8 |
action_result.data.\*.ip_blacklist.blacklist | string | | yes |
action_result.data.\*.ip_blacklist.latest_site_visit_date | string | | 29 Oct 2016 |
action_result.data.\*.ip_blacklist.latest_thread | string | | Fake Google Bot |
action_result.data.\*.location.countryID | string | | USA |
action_result.data.\*.location.countryIcon | string | `url` | https://myip.ms/images/devices/16/flags/USA.png |
action_result.data.\*.location.countryName | string | | United States |
action_result.data.\*.not_working_websites_on_ip.\*.date_when_website_was_using_ip | string | | 10 Jun 2017 |
action_result.data.\*.not_working_websites_on_ip.\*.image | string | `url` | https://myip.ms/images/popularity/rating4.png |
action_result.data.\*.not_working_websites_on_ip.\*.rank | string | | 228287 |
action_result.data.\*.not_working_websites_on_ip.\*.text | string | | 3,720 visitors per day on 10 Jun 2017 |
action_result.data.\*.not_working_websites_on_ip.\*.visitors | numeric | | 3720 |
action_result.data.\*.not_working_websites_on_ip.\*.website | string | | qqwuhan.com |
action_result.data.\*.os_on_ip.\*.os | string | | GNU/Linux x64 |
action_result.data.\*.os_on_ip.\*.osIcon | string | `url` | https://myip.ms/images/os/0/5.png |
action_result.data.\*.owners.owner.address | string | | 1600 Amphitheatre Parkway, Mountain View, CA, 94043, US |
action_result.data.\*.owners.owner.cidr | string | | 8.8.8.0/24 |
action_result.data.\*.owners.owner.countryID | string | | USA |
action_result.data.\*.owners.owner.countryIcon | string | `url` | https://myip.ms/images/devices/16/flags/USA.png |
action_result.data.\*.owners.owner.countryName | string | | USA |
action_result.data.\*.owners.owner.link | string | `url` | https://myip.ms/view/ip_owners/617 |
action_result.data.\*.owners.owner.logo | string | `url` | https://myip.ms/docs/ip_owners/1/google_inc_logo.png |
action_result.data.\*.owners.owner.ownerName | string | | Google Inc |
action_result.data.\*.owners.owner.phone | string | | +1-650-253-0000 |
action_result.data.\*.owners.owner.provider | string | | |
action_result.data.\*.owners.owner.range | string | | 8.8.8.0 - 8.8.8.255 |
action_result.data.\*.owners.owner.rangeSize | string | | 256 |
action_result.data.\*.owners.owner.screenshot | string | `url` | https://myip.ms/docs/ip_owners/1/google-inc.png |
action_result.data.\*.owners.owner.sites | string | | 130006 |
action_result.data.\*.owners.owner.topSites | string | | 1848 |
action_result.data.\*.owners.owner.website | string | | sites.google.com |
action_result.data.\*.owners.parent_owner.address | string | | 1025 Eldorado Blvd. Broomfield, CO, 80021, US |
action_result.data.\*.owners.parent_owner.cidr | string | | 8.0.0.0/8 |
action_result.data.\*.owners.parent_owner.countryID | string | | USA |
action_result.data.\*.owners.parent_owner.countryIcon | string | `url` | https://myip.ms/images/devices/16/flags/USA.png |
action_result.data.\*.owners.parent_owner.countryName | string | | USA |
action_result.data.\*.owners.parent_owner.link | string | `url` | https://myip.ms/view/ip_owners/99 |
action_result.data.\*.owners.parent_owner.logo | string | `url` | https://myip.ms/docs/ip_owners/level_3_communications_inc_logo.png |
action_result.data.\*.owners.parent_owner.ownerName | string | | Level 3 Communications, Inc |
action_result.data.\*.owners.parent_owner.phone | string | | +1-877-453-8353, +1-303-414-5000 |
action_result.data.\*.owners.parent_owner.provider | string | | |
action_result.data.\*.owners.parent_owner.range | string | | 8.0.0.0 - 8.255.255.255 |
action_result.data.\*.owners.parent_owner.rangeSize | string | | 16777216 |
action_result.data.\*.owners.parent_owner.screenshot | string | `url` | https://myip.ms/docs/ip_owners/level3com.jpg |
action_result.data.\*.owners.parent_owner.sites | string | | 5774 |
action_result.data.\*.owners.parent_owner.topSites | string | | 167 |
action_result.data.\*.owners.parent_owner.website | string | | www.level3.com |
action_result.data.\*.query | string | `ip` `ipv6` | 8.8.8.8 |
action_result.data.\*.statistics.total_browsers_on_ip | numeric | | 11 |
action_result.data.\*.statistics.total_dns_on_ip | numeric | | 14 |
action_result.data.\*.statistics.total_not_working_websites_on_ip | string | | 98 |
action_result.data.\*.statistics.total_os_on_ip | numeric | | 8 |
action_result.data.\*.statistics.total_useragents_on_ip | numeric | | 11 |
action_result.data.\*.statistics.total_websites_on_ip_before | string | | 635 |
action_result.data.\*.statistics.total_websites_on_ip_now | string | | 343 |
action_result.data.\*.status | string | | ok |
action_result.data.\*.useragents_on_ip.\*.browser | string | | Firefox 48 |
action_result.data.\*.useragents_on_ip.\*.browserIcon | string | `url` | https://myip.ms/images/browsers/6/2669.png |
action_result.data.\*.useragents_on_ip.\*.latest_site_visit_date | string | | 10 Dec 2017 |
action_result.data.\*.useragents_on_ip.\*.os | string | | Windows 10 x64 Edition |
action_result.data.\*.useragents_on_ip.\*.osIcon | string | `url` | https://myip.ms/images/os/7/2874.png |
action_result.data.\*.useragents_on_ip.\*.useragent | string | | Mozilla/5.0 (Windows NT 10.0; WOW64; rv:48.0) Gecko/20100101 Firefox/48.0 |
action_result.data.\*.websites_on_ip_before.\*.date_when_found_that_website_changed_ip | string | | 10 Mar 2013 |
action_result.data.\*.websites_on_ip_before.\*.date_when_website_was_using_ip | string | | 13 Feb 2013 |
action_result.data.\*.websites_on_ip_before.\*.image | string | `url` | https://myip.ms/images/popularity/rating1.png |
action_result.data.\*.websites_on_ip_before.\*.rank | string | | 967398 |
action_result.data.\*.websites_on_ip_before.\*.text | string | | 332 visitors per day on 13 Feb 2013 |
action_result.data.\*.websites_on_ip_before.\*.visitors | numeric | | 332 |
action_result.data.\*.websites_on_ip_before.\*.website | string | | test.com |
action_result.data.\*.websites_on_ip_now.\*.image | string | `url` | https://myip.ms/images/popularity/rating5.png |
action_result.data.\*.websites_on_ip_now.\*.rank | string | | 57227 |
action_result.data.\*.websites_on_ip_now.\*.text | string | | 9,130 visitors per day |
action_result.data.\*.websites_on_ip_now.\*.visitors | string | | 9130 |
action_result.data.\*.websites_on_ip_now.\*.website | string | | www.myp2pch.net |
action_result.summary.found | boolean | | True False |
action_result.message | string | | Found: True |
summary.total_objects | numeric | | 1 |
summary.total_objects_successful | numeric | | 1 |

______________________________________________________________________

Auto-generated Splunk SOAR Connector documentation.

Copyright 2025 Splunk Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing,
software distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and limitations under the License.
