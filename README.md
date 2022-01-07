[comment]: # "Auto-generated SOAR connector documentation"
# Kaspersky Threat Intelligence

Publisher: Kaspersky Lab  
Connector Version: 2\.0\.2  
Product Vendor: Kaspersky Lab  
Product Name: Kaspersky Threat Intelligence Portal  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 4\.9\.39220  

Kaspersky Threat Intelligence Portal provides reliable, immediate intelligence about cyber\-threats, legitimate objects, their interconnections and indicators, enriched with actionable context to inform your business or clients about the associated risks and implications

[comment]: # " File: readme.md"
[comment]: # ""
[comment]: # "Licensed under Apache 2.0 (https://www.apache.org/licenses/LICENSE-2.0.txt)"
[comment]: # ""
Now you can mitigate and respond to threats more effectively, defending your system against attacks
even before they are launched.  
  
By using this product you agree to the following terms:

1\) The following data is automatically processed for the purpose of providing the product’s main
capabilities, including analysis of URLs, IP addresses, domains, and hashes:

a\) The user name and password to gain access to [Kaspersky Threat Intelligence
Portal](https://tip.kaspersky.com)

b)Data sent to [Kaspersky Threat Intelligence Portal](https://tip.kaspersky.com) for checking. For
more information, refer to [Online
Help.](https://click.kaspersky.com/?hl=en-US&link=online_help&pid=KTIPSP&version=1.0&helpid=184492)

  

2\) You do not submit any personal data to Kaspersky Threat Lookup Service because this data is not
required for the provision of the above stated capabilities. Privacy Policy, which describes the
processing of data: [Privacy Policy](https://www.kaspersky.com/products-and-services-privacy-policy)

  
On-line documentation for Kaspersky Threat Intelligence Portal applicant for Splunk Phantom: 
[link](https://click.kaspersky.com/?hl=en-US&link=online_help&pid=KTIPSP&version=1.0&helpid=184492)  
  
**Note** : If you have a PFX-formatted certificate to access Kaspersky Threat Intelligence Portal,
you should convert it to PEM format as described at  [KL TIP on-line
documentation](https://tip.kaspersky.com/help/Doc_data/ConvertingCertToPEM.htm)  


### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a Kaspersky Threat Intelligence Portal asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**username** |  required  | string | Portal user name
**password** |  required  | password | Portal password
**pem\_key** |  required  | file | PEM certificate for Kaspersky Threat Intelligence Portal
**records\_count** |  required  | numeric | Maximum number of records to display
**accept\_the\_terms\_and\_conditions** |  optional  | boolean | I understand and accept the Terms and Conditions
**accept\_privacy\_policy** |  optional  | boolean | I understand and accept Privacy Policy

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration  
[domain reputation](#action-domain-reputation) - Looks up information about domains in Kaspersky Threat Intelligence Portal  
[ip reputation](#action-ip-reputation) - Looks up information about IP addresses in Kaspersky Threat Intelligence Portal  
[file reputation](#action-file-reputation) - Looks up information about hashes in Kaspersky Threat Intelligence Portal  
[url reputation](#action-url-reputation) - Looks up information about URLs in Kaspersky Threat Intelligence Portal  
[get detailed info](#action-get-detailed-info) - Queries detailed information about indicator  
[get reports](#action-get-reports) - Requests APT reports by using the Kaspersky Threat Intelligence Portal API  

## action: 'test connectivity'
Validate the asset configuration for connectivity using supplied configuration

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'domain reputation'
Looks up information about domains in Kaspersky Threat Intelligence Portal

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**domain** |  required  | Domain to query | string |  `domain` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.domain | string |  `domain` 
action\_result\.data\.\*\.DomainGeneralInfo\.Categories | string | 
action\_result\.data\.\*\.DomainGeneralInfo\.HasApt | boolean | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary\.zone | string | 
action\_result\.summary\.apt\_report | string | 
action\_result\.summary\.apt\_report\_id | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'ip reputation'
Looks up information about IP addresses in Kaspersky Threat Intelligence Portal

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip** |  required  | IP to query | string |  `ip` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.ip | string |  `ip` 
action\_result\.data | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary\.zone | string | 
action\_result\.summary\.threat\_score | numeric | 
action\_result\.summary\.categories | string | 
action\_result\.summary\.apt\_related | boolean | 
action\_result\.summary\.apt\_report | string | 
action\_result\.summary\.apt\_report\_id | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'file reputation'
Looks up information about hashes in Kaspersky Threat Intelligence Portal

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**hash** |  required  | File hash to query | string |  `hash`  `sha256`  `sha1`  `md5` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.hash | string |  `hash`  `sha256`  `sha1`  `md5` 
action\_result\.data | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary\.hash | string |  `hash` 
action\_result\.summary\.sha1 | string |  `hash` 
action\_result\.summary\.sha2 | string |  `hash` 
action\_result\.summary\.zone | string | 
action\_result\.summary\.categories | string | 
action\_result\.summary\.apt\_related | boolean | 
action\_result\.summary\.apt\_report | string | 
action\_result\.summary\.apt\_report\_id | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'url reputation'
Looks up information about URLs in Kaspersky Threat Intelligence Portal

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** |  required  | URL to query | string |  `url` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.url | string |  `url` 
action\_result\.data | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary\.zone | string | 
action\_result\.summary\.categories | string | 
action\_result\.summary\.apt\_related | boolean | 
action\_result\.summary\.apt\_report | string | 
action\_result\.summary\.apt\_report\_id | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'get detailed info'
Queries detailed information about indicator

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**indicator** |  required  | Indicator to query | string |  `url`  `hash`  `sha256`  `sha1`  `md5`  `domain`  `ip` 
**sections** |  optional  | Sections to query | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.indicator | string |  `url`  `hash`  `sha256`  `sha1`  `md5`  `domain`  `ip` 
action\_result\.parameter\.sections | string | 
action\_result\.data | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary\.tip\_url | string | 
action\_result\.summary\.hits\_count | numeric | 
action\_result\.summary\.apt\_report | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'get reports'
Requests APT reports by using the Kaspersky Threat Intelligence Portal API

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**apt\_id** |  required  | APT ID | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.apt\_id | string | 
action\_result\.data | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary\.apt\_report | string | 
action\_result\.summary\.apt\_url | string | 
action\_result\.summary\.apt\_report\_desc | string | 
action\_result\.summary\.apt\_report\_geo | string | 
action\_result\.summary\.apt\_report\_industry | boolean | 
action\_result\.summary\.apt\_report\_actors | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 