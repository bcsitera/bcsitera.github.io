---
---
# Smart-ID User Guide

## Table of Contents
- [Setup](#setup)
- User Guide

## Setup

### Adding and Managing Users

“Refresh Users” checks whether the list of _Smart-ID Users_ matches the list of general system _Users_. If users have been added or removed from BC, this action will refresh the _Smart-ID User_ list. 

“Update Users“ saves the data assigned to users in the _Smart-ID User_ list, such as Personal, Country, and Language Codes and authentication necessity, to Business Central. The given information can be assigned to users by opening the list via the field “No. of Users”.

### Authentication and Signing

To allow authentication, it must be enabled on the setup page on company level. However, it is possible to specify separately for each user in the _Smart-ID User_ list whether authentication is required at login. In short, enabling authentication requires double-verification, as it is subject to a different pricing scheme. To learn about the authentication pricing, please contact [BCS Itera](#contact-information).

Both authentication and signing can be configured with additional settings. In both cases, you can enable the confirmation message as well as the confirmation code choice options. For the former, a confirmation window appears when opening Smart-ID - the confirmation message can be set under “Display Text”.

<div style="text-align: center;">

<img src="https://raw.githubusercontent.com/wiki/SK-EID/smart-id-documentation/images/confirmationMessage_1.png" width="45%" /><br>  

<em>Authentication/Signing Confirmation Needed</em>

</div>

In the latter case, not only is the verification code displayed in the Smart-ID app but in order to complete the operation, the correct one must be selected from a choice of three codes. Neither setting is supported by every version of the Smart-ID app and usage depends on the user's device.

<div style="text-align: center;">

<img src="https://raw.githubusercontent.com/wiki/SK-EID/smart-id-documentation/images/confirmationMessageAndVerificationCodeChoice_1.png" width="45%" /><br>  

<em>Authentication/Signing Code Choice Needed</em>

</div>

When signing, pre-authentication can also be enabled, i.e. in addition to signing using PIN2, the user must also authenticate themselves beforehand, i.e. use PIN1.

---

### Contact Information
For more information and pricing please contact:  
[https://apps.itera.ee/docs/en-us/support](https://apps.itera.ee/docs/en-us/support)
