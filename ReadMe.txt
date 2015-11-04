SimpleStickiesUsingISyncSessionDriver is an application that uses Sync Services to sync Note records locally and over .Mac. 

The application allows you to create simple Note records that are displayed in a table view. The application demonstrates the use of the ISyncSessionDriver class. It syncs whenever it saves the records to a local file. It also uses the ISyncSessionDriver automatic alert handling so it syncs whenever another app, device, server, or peer syncs the same schema.

Note: You should sync the Stickies schema over .Mac from one instance of SimpleStickiesUsingISyncSessionDriver to another running on another computer to demonstrate pushing and pulling records.

Follow these steps on each computer to test SimpleStickies over .Mac:

1) Launch SimpleStickiesUsingISyncSessionDriver

2) Open System Preferences and select .Mac

3) Choose Sync and select the Stickies schema.

4) Select "Show status in menu bar" to display the sync icon in the menu bar.

5) Using SimpleStickiesUsingISyncSessionDriver, click the Add button to add Note records.

6) Edit other Note properties in the detail area at the bottom of this window.

7) Select File > Sync (command-S) to save and sync the records to the truth database.
   Verify that records are pushed to the truth using Syncrospector.

8) Choose Sync Now from the sync icon that appears on the menu bar.
   Verify that records are pushed to .Mac and pulled by the other computer. Note that SimpleStickiesUsingISyncSessionDriver should sync whenever.Mac syncs.


Cleanup for SimpleStickiesUsingISyncSessionDriver

Follow these steps to restore the truth and SimpleStickiesUsingISyncSessionDriver to it's initial state. You can do this without affecting other apps, schemas and .Mac as follows:

1) Exit the SimpleStickiesUsingISyncSessionDriver application

2) Remove the application data:

rm ~/Library/Application\ Support/SyncExamples/com.mycompany.SimpleStickies.xml

3) Unregister the clients for SimpleStickies from the Client panel (command-1) in Syncrospector. The client identifier is com.mycompany.SimpleStickies.

4) Unregister the Schema for Stickies from the Schema Panel (command-6) in Syncrospector. The Schema is named com.mycompany.Stickies


Core SimpleStickiesUsingISyncSessionDriver Classes:

AppDelegate--the Cocoa application and window delegate. It is also the ISyncSessionDriver delegate and data source. This class creates the window containing the table of Note records. Use this window to create and update Note records.

MainMenu.nib--contains the Cocoa main menu and Note window with the table view. Contains the AppDelegate object.


