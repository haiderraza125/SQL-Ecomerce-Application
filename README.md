# SQL-Ecomerce-Application
About the DWH of the application.
How Data is stored on DWH on new registeration or existing user use. 
The complete schema of DWH can also be seen in file DWH-Application
During a user’s lifecycle, before as well as after registering on the platform, any visits of platform webpages are tracked (if possible).
In the informations table the total amount of page visits is stored (info_page_visits) for the respective timestamp of the visit and the respective used device (phone, tablet, desktop, etc.).
At the moment the user registers on the platform, a row is created in the users table. Additionally, in case the user visited the platform before, rows are created in the activities table for all of the user’s previous visits with the respective device_ID and timestamp of the visit (activity_timestamp = info_timestamp). After the registration any user activity on the platform is also stored in the activities table. The activity_is_last field is updated accordingly and always true for only one row per user in this table.
When the registered user buys something on the platform, this creates a row in the sales table and when the item is paid, a row in the payments table.
