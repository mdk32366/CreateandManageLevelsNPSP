### CreateandManageLevelsNPSP
Setting up giving levels in NPSP

[Power of One Post](https://powerofus.force.com/articles/Resource/NPSP-Create-and-Manage-Levels)

Create Levels
You only need to set up your levels once and thereafter NPSP will monitor the fields you've selected and automatically update related Level fields on a nightly basis.

Click the Levels tab. (If you don't see it, click More icon, then click All Items.)
You can review already created Levels on this page or from a custom list view.
Click New to create a new Level. You'll see a special interface designed to help you select the correct fields without knowing the API Developer Name.
Create Level screen
Level Name (1)—The Name that will appear in the Level field on the Account, Contact, or other object you've chosen. You must type in a name before you can enter any other fields.
Note
If you select the Target object before entering a name, you won't see values in any of the other drop-down fields. To fix this issue, clear all of the fields and enter the Level Name. You'll then be able to select a Target object and other values.
Target (2)—The object that this level applies to. Select either Account, Contact, or other object you've chosen. See Enable Levels on Other Objects for how to add additional objects.

Source Field (3)—The field that will be totaled across all records to determine what Level the Contact or Account is in. For our example, we selected Total Gifts (a currency field) however you can select any currency or number field.

Level Field (4)—Remember that custom field you created earlier? Here's where you select it. If you don't have a Level field, you'll need to create one.

Previous Level Field (5)—This field is optional. It stores the previous Level value if the Level changes. Select the custom Previous Level field you created earlier.

Minimum and Maximum Amount (6)—This defines the range of this Level. You can leave Minimum blank to cover all up to (but not including) the Maximum Amount. Likewise, you can leave Maximum Amount blank to cover all amounts over (and including) the Minimum Amount (such as your very top level). Remember, Amount is not necessarily currency.

Engagement Plan Template (7)—If you want to have a series of Task Activities that are automatically generated when a Contact or Account reach a certain Level, this is where you would select that Engagement Plan. See Create and Manage Engagement Plans for information on configuring and using Engagement Plans.

Make sure Active is checked and give your Level an appropriate Description (8).

If this is the first Level you're creating, click Save & New. This will automatically clone the existing Level and adjust the Maximum and Minimum values. Just give the new Level a name. You can very quickly set up a series of Levels this way. Click Save on the final Level.
Enable Levels on Other Objects
You can add Levels to other objects by including additional picklist values on the Target field on the Levels object.

In Setup, click the Object Manager tab.
In the list of objects, click Level.
Click Fields & Relationships.
In the list fields, click Target.
In the Values section, click New.
New button on Target picklist values
Enter the API name (not the label) for the object. For example, if your custom object has the label of Registrants (that's what appears on your tab), and has the API name of Registrants__c, you would add Registrants__c as a picklist value for that field.
API name of Registrants__c as a picklist value
Click Save.
Don't forget to create Level fields on the object after enabling it.

Manually Recalculate Levels
That's it! Now, as the Source Field changes on your Account or Contacts, Levels are automatically calculated (on a nightly basis). Due to the processing involved, Levels are not applied instantly. Instead, Levels will be updated as part of the nightly batch process that NPSP runs. However, at any time you can update all your records with the correct Levels. Simply navigate to NPSP Settings | Bulk Data Process | Level Assignment Batch and click Run Batch.

Note
The Level Assignment Batch only recalculates Levels for Accounts or Contacts that were updated since that last time the batch was run. There are a few exceptions:
If a Level record is updated (for example, you change the Level name or threshold), the job will recalculate all related Levels.
If a Level references any formula fields, the job will always recalculate that Level.
The default batch size for the Level Assignment Batch is 200. You can change the batch size as needed. Simply navigate to NPSP Settings | Bulk Data Processes | Batch Process Setting and update the value in the Level Assignment Batch Size field.
