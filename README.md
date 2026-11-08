# Carrie's Guide to MeshCore
A braindump of all the things I wish I knew when I first got on the Mesh!  Radio settings are for SLO and the rest are my suggestions for a good time.

If you don't have a device yet, here's a [Shopping List](MeshCore%20Shopping%20List.md).  Almost any Meshtastic device can be re-flashed with MeshCore firmware.  All the radio gear is the same.

## Flashing MeshCore:
* Go here to reflash it: https://flasher.meshcore.io/
* Plug your device into your computer via USB
* Scroll down, choose your device.
* Then choose Companion Bluetooth.
* Click "Enter DFU Mode".  Your browser will ask to allow serial port access, probably Tiny USB.  Click Allow.
* If a folder window pops up with a D: drive containing UF2 files, ignore it.
* Then click Flash!.
* Another serial port pop-up will happen, probably saying nRF something, click Allow.
* Wait for flashing to be done, don't disconnect the USB cable until you see a Flash Complete! message.  Then you're good!

If the Enter DFU Mode button doesn't work, you can do it from the device.  Usually you double-click the device's reset button, if that doesn't work, refer to your device's manual.

## Using the MeshCore app:
* Download it.  It should just be called MeshCore.
* Make sure Bluetooth is turned on, but don't pair anything from your phone's Bluetooth settings panel.
* Go to the app to pair it.  If your device doesn't have a screen, the pairing code is 123456.  Otherwise the code will be shown on the screen.
* If it asks you to choose a preset or area of the world, choose USA.

## Settings:
* Click the gear, that will get you into settings for your node.
* Rename the node, that will be your visible handle that other people see.
* Don't worry if there's no GPS position, you can turn this on/off below.
* I'd recommend leaving "Share Position in Advert" unchecked unless you want everyone on the mesh to know where you are when you send an advert.  This can be fun to do if you're hiking or something and not in your actual house.

## Make sure your Radio Settings are those of your region.  San Luis Obispo uses:
* Frequency: 910.525 MHz
* Bandwidth: 62.5 kHz
* Spreading Factor: 7
* Coding Rate: 5
* Enable Repeat Mode should always be OFF (unchecked)

## Network Settings:
* set Default Path Hash Size to 2-byte (this is explained more below)

## Contact Settings:
* select Auto Add All and Overwrite Oldest

## Notification Settings:
* set to whatever you want.  Note that "New Contact Discovered" will include repeaters, and this will notify its head off for the first few days you're connected.
* You probably want Contact Messages and New Messages while Disconnected.

## Position Settings:
You can enable or disable GPS (assuming your node has GPS).  Even with GPS enabled, there's the choice to share your position or not when you send a public advert (I'd recommend leaving that off).

# Now send some messages! 

## Channels:
* Go to Channels.  Public should be there by default.  From the 3 dot menu, add two hashtag channels: #test and if you are around San Luis Obispo, #slo (other cities will have local channels, dig around the internet for what yours is).
* Send the word "test" in #test.  It will automatically say "Sent" underneath, this just confirms that your device sent out the message, not that anyone heard it.  If it says "Heard X Repeats" then yay, you're getting on the network!  You will hopefully after maybe 10-30 seconds get a response from a repeater bot somewhere that tells you where it is and how many hops your message took to get there.  If it remains on "Sent" after a minute, try again.  The Mesh is still a bit holey and not super consistent.  If you aren't able to get any "Heard X Repeat" messages, you might not be able to see a repeater from where you are.  Use #test anytime, especially if you're not sure if the mesh is hearing you.
* Feel free to send messages in #slo and #public!  You should start receiving some too.  If you receive messages, then you are hearing a repeater even if it can't hear you!  Some times of day are more chatty and some are more quiet, so give it a few minutes.  These (and #test) are public non-encrypted channels that anyone can join and see.  The shorter the message you send, the better chance it has of getting out on the mesh.
* When you receive a message, tap and hold, and then choose "View Message Paths".  At first, it'll all say "Unknown Repeater", but you can get an idea of how far away that person is by the number of hops it takes to get to them.  After a couple of days when your map is populated, you'll be able to see the path the signal traveled using Map View.  If there are 2 or more paths shown, cool!  That means you received the message through a few different repeaters.  Check them all out to learn more about your local area.
* There are Channel Settings under the 3 dot menu, you can change notifications for each channel and also set how long your phone keeps the messages around.  For Public and #hashtag channels, you might want to set this to just a few days instead of "Keep All".

## How the Map Works and How Repeaters Behave:
* At first, you will see nothing on the map.  Don't panic!  This is normal.  You'll have to keep your node on and in good range of a repeater for a few days for your map to populate.  Why?
* Repeaters only send out identifying information (incl name and location) once or twice a day.  They don't do it more often because you don't want the mesh clogged up with repeater announcements.  If your node isn't on or isn't in range when a repeater sends this info, you'll miss it.  A repeater will only appear on the map once it hears this announcement.  But it'll still pass on messages, your node will still hear and use it.  It'll just show up in the path list as "Unknown Repeater".
* A good thing to do when in a new spot is to go into the main 3 dot menu, select Tools, then Discover Nearby Nodes, then Discover Repeaters.  This will populate with a list of repeaters your node can directly hear.  I think you can request the name of the repeater if it's still "Unknown" but I don't think you'll get the location, so it still may not show up on your map until you hear it's official advert.
* Above, I recommended setting the "Default Path Hash Size" to 2.  This is getting into the weeds, but it's important to know.  Repeaters have unique IDs that are very long.  To not clog up the mesh, they just add the first few bytes of their ID to messages, so you can identify the message path.  But we can see so many repeaters all over California, that we need to use 2 bytes instead of just 1 byte to identify them, because many repeaters have the same first byte.  If you only have 1 byte enabled and look at a mapped signal path, it'll be all over the place because it won't know which repeater it actually went through.  Setting your path size to 2 bytes can affect your mesh connectivity a little bit - if repeaters in the area haven't been updated in a while and are still set to 1 byte, they'll drop your message.  But the local SLO repeaters are almost all using 2 byte codes, so you should be fine.  If you have a lot of trouble connecting to the mesh, you can try setting your node to 1 byte.  You'll then be able to use both 1 byte AND 2 byte repeaters.  But your signal paths will be hard to understand.

## Discover Contacts and its Map vs normal Contacts and Map vs Internet Map:
* Under the 3 dot menu, you'll see Discover Contacts.
* This Discover Contacts list and map view are for everyone you're ever heard, not just those you've added as a Contact.
* OK whoa, this is confusing, what's going on?
* In Contact Settings several sections above, we're automatically adding everything we hear to our Contacts list, and that's what the main Map is showing us.  This is a convenient way of quickly understanding where repeaters are in your local area.  But at some point, we'll hit the ~350 Contacts limit that most devices have for onboard storage.  So that's why we Overwrite Oldest which also preserves anyone on your Favorites list.  Your main Contacts and Map will always be a snapshot of what's around recently.
* The Discover Contacts I believe is stored on your phone, and will show everyone and every repeater you've ever heard.
* Under the 3 dot menu you'll also see Internet Map.  This is what has been reported to the Mesh, so you can use this to see if there are any repeaters around you that you *should* be seeing.

## Contacts & Channels Sending Encrypted Messages:
* Add Contacts is under the 3 dot menu.
* You can add someone as a Contact by scanning or exchanging QR codes
* You can also send an "advert" to the mesh which is public and everyone in range will hear.  Both of you will have to do this so you can add each other as Contacts.
* You can also copy/paste and email or (using your normal cell network) text someone your public key.
* Be sure to Favorite your new friend so they don't get overwritten by repeaters in your list.
* Once you've both added each other as Contacts, any messages sent between you are encrypted.
* Add Channel is under the 3 dot menu.
* You can create or join a Private Channel which is essentially a private encrypted group chat.

## Meshtastic vs MeshCore:
* Meshtastic is all device-to-device communication.  It's great for temporary adhoc netwokrs, or small networks in remote places.  The issue with Meshtastic is that it doesn't scale - every device repeats everything it hears, so if you have a lot of people in one area all talking, the bandwidth gets used up fast.
* MeshCore attempts to solve this by using a system of repeaters to pass along messages.  Each device communicates with a repeater, the repeaters rebroadcast the message.  This allows a network of repeaters to cross long distances and connect larger user bases together.  There are still issues with scaling and repeaters getting overloaded, but it's a lot more robust and useful for fixed infrastructure situations (like comms within or between cities).
* Since Meshtastic is all device to device, the map populates quickly as each person sends messages.  You can get an idea of how many people are on Meshtastic in your area pretty fast.  Since Meshcore relies on repeaters to identify themselves and users are invisible (unless they make a public advert), it takes a little longer for the map to populate and for you to get an idea of Meshcore infrastructure in your area.
* Meshtastic has a really nice feature of automatically obfuscating your GPS location, and allowing you to choose the level of obfuscation.  So people see where your location is within a few km.  MeshCore doesn't have this, and has sharing location turned OFF by default.  If you enable it, you can choose to what to put as your GPS location - it can be your actual location, or you can make something up.  And that's only if you choose to manually send a public advert.  So you generally won't see many users on your map, or on your contacts lists.
* To get an idea of the local MeshCore scene, go to the Public channel and see what the chatter is like.  Go to the Internet Map and see how many repeaters are in your area.  Make sure you have good repeater coverage.  There are LOTS of people on MeshCore, even here in SLO which is a small town for California.  if you're not seeing anything, you likely don't have a good connection to a repeater.

# Have fun chatting with randos on the radio!
