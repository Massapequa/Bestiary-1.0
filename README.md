# Bestiary-1.0
An in-game bestiary that catalogues the various creatures you'll encounter around the world.<br>
<br>
This is a C# script for the Ultima Online emulator ServUO (www.ServUO.com)<br>
<details>
  <summary>
    Usage:
  </summary>
A simply UI that acts as a catalogue for the various creatures you can encounter in your world!<br>
It can be accessed with the player-level command "[bestiary"<br>
</details>
<details>
  <summary>
    Preview Links:
  </summary>
  
[List Preview](https://www.deviantart.com/massapequa/art/Bestiary1-1019458668) <br>
[Entry Preview 1](https://www.deviantart.com/massapequa/art/Bestiary2-1019460621) <br>
[Entry Preview 2](https://www.deviantart.com/massapequa/art/Bestiary3-1019461026) <br>

</details>

<details>
  <summary>
    Adding Entries:
  </summary>
  There's 3 locations you'll have to edit to add your own entry.<br>
<br>
Go into Bestiary.cs and find these lines:<br>


		static Bestiary()
		{
			_Entries = new BestiaryEntry[126];

Don't forget to change that number (126) to reflect the total number of entries you've added when you're done.<br>

At the bottom of the entries list, add your own entry:<br>
example:<br>

			_Entries[126] = new 	MyCustomCreatureEntry();

<br>
Then, under that, find the list of entries that looks like this:<br>

		public static BestiaryEntry ArcticOgreLordEntry
        {
            get
            {
				return _Entries[0];
			}
	    }

Go to the bottom of the list and add your own:

		public static BestiaryEntry MyCustomCreatureEntry
        {
            get
            {
				return _Entries[126];
			}
	    }


Finally, scroll down to the bottom of the script and add your creature's information.<br>
Right below the last entry, add your own:<br>

	public class MyCustomCreature : BestiaryEntry
	{
		public override string Name { get { return "My Custom Creature"; } }
		public override int BodyID { get { return *bodyvalue here*; } }
		public override Type CreatureType { get { return Type.Beast; } } // types include Abyssal, Beast, Elemental, Fey, Humanoid, Monster, or Undead
		public override string Description { get { return "Your description here."; } }
	}


In your Entry, you can either use your creature's BodyID, which will be looked u in teh shrink table, 
or you can use:<br>

		public override int ItemID { get { return *any ItemID here*; } }

To put any item in place of where the small icon of the monster will go.
</details>
