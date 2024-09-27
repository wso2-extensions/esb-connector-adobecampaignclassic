# Profiles.md

# Working with Profiles in Adobe Campaign Classic Connector

[Overview](#overview) | [Operation Details](#operation-details)

## Overview

The following operations allow you to work with Profiles in Adobe Campaign Classic. A Profile represents a recipient or customer in your database. Click an operation name to see details on how to use it.

| Operation       | Description                              |
|-----------------|------------------------------------------|
| [createProfile](#creating-profiles)  | Creates a new profile in Adobe Campaign Classic. |
| [updateProfile](#updating-profiles)  | Updates an existing profile in Adobe Campaign Classic. |
| [getProfile](#retrieving-profiles)   | Retrieves a profile by ID from Adobe Campaign Classic. |

---

## Operation Details

This section provides further details on the operations related to Profiles.

### Creating Profiles

To create a new profile, use `adobeCampaignClassic.createProfile` and specify the following properties.

#### createProfile

```xml
<adobeCampaignClassic.createProfile configKey="MyACCConfig">
    <email>{$ctx:email}</email>
    <firstName>{$ctx:firstName}</firstName>
    <lastName>{$ctx:lastName}</lastName>
</adobeCampaignClassic.createProfile>
```

#### Properties

- **email**: Email address of the profile. (Required)
- **firstName**: First name of the profile. (Optional)
- **lastName**: Last name of the profile. (Optional)


#### Sample Response

Given below is a sample response for the `createProfile` operation.

```xml
      <xtk:SaveResponse>
         <pdomOutput>
            <recipient id="12345">
               <email>john.doe@example.com</email>
               <firstName>John</firstName>
               <lastName>Doe</lastName>
            </recipient>
         </pdomOutput>
      </xtk:SaveResponse>
```

### Updating Profiles

To update an existing profile, use `adobeCampaignClassic.updateProfile` and specify the following properties.

#### updateProfile

```xml
<adobeCampaignClassic.updateProfile configKey="MyACCConfig">
    <profileId>{$ctx:profileId}</profileId>
    <email>{$ctx:email}</email>
    <firstName>{$ctx:firstName}</firstName>
    <lastName>{$ctx:lastName}</lastName>
</adobeCampaignClassic.updateProfile>
```

#### Properties

- **profileId**: ID of the profile to update. (Required)
- **email**: Email address of the profile. (Optional)
- **firstName**: First name of the profile. (Optional)
- **lastName**: Last name of the profile. (Optional)
- **Additional fields**: Any other profile fields as needed.

#### Sample Response

```xml
      <xtk:SaveResponse>
         <pdomOutput>
            <recipient id="12345">
               <email>jane.smith@example.com</email>
               <firstName>Jane</firstName>
               <lastName>Smith</lastName>
            </recipient>
         </pdomOutput>
      </xtk:SaveResponse>
```

### Retrieving Profiles

To retrieve a profile by ID, use `adobeCampaignClassic.getProfile` and specify the following properties.

#### getProfile

```xml
<adobeCampaignClassic.getProfile configKey="MyACCConfig">
    <profileId>{$ctx:profileId}</profileId>
</adobeCampaignClassic.getProfile>
```

#### Properties

- **profileId**: ID of the profile to retrieve. (Required)

#### Sample Response

```xml
      <xtk:ReadResponse>
         <pdomOutput>
            <recipient id="12345">
               <email>user12345@example.com</email>
               <firstName>FirstName12345</firstName>
               <lastName>LastName12345</lastName>
            </recipient>
         </pdomOutput>
      </xtk:ReadResponse>
```
