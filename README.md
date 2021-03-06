# Text Expander JS (Obsidian Plugin) - Shortcut-file library

These are sample shortcut-files for the Obsidian plugin [Text Expander JS](https://github.com/jon-heard/obsidian-text-expander-js).

The easiest way to use these shortcut-files in your Obsidian vault is to click the "Import Full Library" button, near the top of the plugin settings, beside "Shortcut-files".  This will download the full library into your vault, after which point you can remove shortcut-files as you wish.

To use an indiviual shortcut-file from this library in your Obsidian vault, you can copy the raw text of the shortcut-file and paste it into a note in your vault.  Then:
1. Make sure that [Text Expander JS](https://github.com/jon-heard/obsidian-text-expander-js) is installed in your vault.
2. Open The Text Expander JS settings.
3. Go to the first setting: "Shortcut-files".
4. Click the "Add file reference" button.  This adds a new textfield below the setting.
5. Type the address of the vault-note into the new textfield.  The textfield will be red until the address is recognized.
6. Close the settings and type `;;help;` (!!help! on mobile) to review the new shortcuts.

## Reference - All shortcut-files in this repo

- [tejs_state](#tejs_state)
- [tejs_lists](#tejs_lists)
- [tejs_varnotes](#tejs_varnotes)
- [tejs_mythicv2](#tejs_mythicv2)
- [tejs_mythicgme](#tejs_mythicgme)
- [tejs_une](#tejs_une)
- [tejs_adventurecrafter](#tejs_adventurecrafter)
- [tejs_rpgtools](#tejs_rpgtools)
- [tejs_clips](#tejs_clips)
- [tejs_arrows](#tejs_arrows)
- [tejs_lipsum](#tejs_lipsum)
- [tejs_support](#tejs_support)

***

### tejs_state
This shortcut-file includes shortcuts that let the user manage a session state.  Effectively allows saving and restoring data between sessions.

This shortcut file can be used by other shortcut-files to help them save/restore their states.

- __reset state__ - Clear all state.
- __state__ - Expands to a string representing the current state (for session saving).
- __state {state}__ - Sets the current state based on {state}: a string created with the parameterless "state" shortcut.

***

### tejs_lists
Shortcuts for working with lists.

- __reset lists__ - Clear all lists.
- __lists__ - Show all list and all items for each list.
- __lists list {list name}__ - Show all items in the list {list name}.
- __lists pick {list name}__ - Get a random item from the list {list name}.
- __lists add {list name} {item}__ - Add {item} to the list {list name}.  Allows duplicate items.
    - Can only add to basic lists and combo lists that contain basic lists.
- __lists remove {list name} {item}__ - Remove an instance of {item} from the list {list name}.
    - Can only remove from basic lists and combo lists that contain basic lists.
- __lists removelist {list name}__ - Remove the entire list {list name}.
- __lists addfolder {list name} {folder}__ - Create a folder-list named {list name} that is linked to the folder {folder}.  A "folder-list" is a list who's items are the names of the notes in the linked folder.
- __lists addcombo {list name} {sub list 1} {sub list 2}...__ - Create a combo-list named {list name} that is linked to the sublists given as {sub list 1}, {sub list 2}, etc.  A "combo-list" is a list who's items are all of the items of its linked sublists.

***

### tejs_varnotes
Setup and manage variables within notes.  Can be used by other shortcut-files for working with data in notes.

- __reset varnotes__ - Removes all stored varnotes from the session state.
- __varnotes__ - Lists all varnotes and the files they are connected to.
- __varnotes vars {varnote name}__ - Lists all the vars for the varnote named {varnote name} (a required name property).
- __varnotes add {varnote name} {file address}__ - Adds a varnote named {varnote name} (a required name parameter) that is attached to the file at {file address} (a required file address parameter).
- __varnotes remove {varnote name}__ - Removes the varnote {var name} (a required name parameter).
- __varnotes get {varnote name} {var name}__ - Gets the value of the var named {var name} (a required name parameter) in the varnote named {varnote name} (a required name parameter).
        Alternative shortcut: __vn {varnote name} {var name}__.
- __varnotes set {varnote name} {var name} {value}__ - Sets the var named {var name} (a required name parameter) to {value} (a required text parameter), in the varnote named {varnote name} (a required name parameter).
        Alternative shortcut: __vnset {varnote name} {var name} {value}__.
- __varnotes refresh__ - Get the latest vars from all varnotes and store it all.
- __varnotes refresh {varnote name}__ - Pull the vars from varnote {varnote name} (a required "name" parameter).

***

### tejs_mythicv2
_(disabled by default, due to incompatibility with tejs_mythicgme)_

Shortcuts for Mythic Variations 2.  This is an excellent "GM emulator" system for solo and GM'less gaming.  You can find more info about Mythic Variations 2 at [wordmill games](http://wordmillgames.com/mythic-variations-2.html).

Incompatible with __tejs_mythicgme__.  If __tejs_mythicgme__ comes before __tejs_mythicv2__ in the shortcut-list, then __tejs_mythicv2__ will be disabled.

- __reset mythicv2__ - Reset mythic state to defaults and displays scene heading.
- __mythicv2 details {state}__ - If {state} is given (must be "y" or "n"), assigns it to the mythicv2 "details" mode.  Otherwise, displays the current "details" mode.
- __detail__ - Make a detail check.
- __event__ - Make an event check.
- __fate {odds} {wanted}__ - Make a fate check based on {odds}: an optional value defaulting to 0 {50/50}.
 It can be from -4 (impossible) to 4 (has to be).  It can also be the specific text of the odds, such as "impossible", "sure thing", etc.
 This shortcut is also based on {wanted}: an optional value of either 'n' or 'y', defaulting to 'y'.  The value {wanted} specifies the direction of the chaos modifier.
        Alternative shortcut: __f {odds} {wanted}__.
- __meaning action__ - Roll on the action meaning table.
        Alternative shortcut: __meaning__.
- __meaning description__ - Roll on the description meaning table.
- __scene__ - Show the current scene.
- __scene {chaosAdjust}__ - Shift the chaos value by {chaosAdjust} (1, 0 or -1), then increment the current scene and run a scene check.
- __chaos__ - Show the current chaos value.
- __chaos--__ - Decrease the chaos value by 1 (minimum of 3).
- __chaos++__ - Increase the chaos value by 1 (maximum of 6).
- __chaos={value}__ - Set the chaos value to {value}, an integer from 3 to 6.
- __descriptor__ - Generates a personality and activity descriptor for an NPC.
- __disposition {descriptor count}__ - Rolls for an NPC's disposition, modified by {descriptor count}: a required parameter representing the total of the NPC's activated descriptors (integer from -3 to 3).
    - Example: 2 positively activated descriptors and 1 negatively activated descriptor would make a {descriptor count} of __1+1+(-1) = 1__.
- __disposition {base} {descriptorCount}__ - Displays the NPC disposition determined by the {base} disposition, modified by {descriptorCount}.  See "disposition {descriptor count}" for an explanation of {descriptor count}.
- __action {dispositionAdjust}__ - Makes an NPC behavior check, modified by {dispositionAdjust}, the modifier of the NPC's disposition.

***

### tejs_mythicgme
Shortcuts for Mythic Game Master Emulator.  Mythic GME is an excellent "GM emulator" system for solo and GM'less gaming.  It was designed by Tana Pigeon.  You can find more info about Mythic GME at [wordmill games](http://wordmillgames.com/mythic-game-master-emulator.html).

Incompatible with __tejs_mythicv2__.  If __tejs_mythicv2__ comes before __tejs_mythicgme__ in the shortcut-list, then __tejs_mythicgme__ will be disabled.

- __reset mythicgme__ - Reset mythic state to defaults and displays scene heading.
- __fate {odds}__ - Make a fate check based on {odds}: an optional value defaulting to 0 (50/50).  It can be from -4 (impossible) to 6 (has to be).  It can also be the specific text of the odds, such as "impossible", "sure thing", etc.
        Alternative shortcut: __f {odds}__.
- __scene__ - Show the current scene.
- __scene {chaosAdjust}__ - Shift the chaos value by {chaosAdjust} (1, 0 or -1), then increment the current scene and run a scene check.
- __event__ - Make an event check.
- __meaning__ - Roll on the meaning tables.
- __chaos__ - Show the current chaos value.
- __chaos--__ - Decrease the chaos value by 1 (minimum of 1).
- __chaos++__ - Increase the chaos value by 1 (maximum of 9).
- __chaos={value}__ - Set the chaos value to {value}, an integer from 1 to 9.

***

### tejs_une
Shortcuts for UNE: The Universal NPC Emulator.  UNE is an excellent character generation system for tabletop role playing and general storytelling.  It was designed by Zach Best. 
 You can find more info about UNE at its [drivethrurpg page](https://www.drivethrurpg.com/product/134163/UNE-The-Universal-NPC-Emulator-rev).

- __une {randomness} {relationship to pc} {demeanor}__ - Runs "une character" and "une interact" together.  {randomness} is an optional value for "une character".  {relationship to pc} and {demeanor} are optional values for "une interact".
- __une character {randomness}__ - Runs "identity", "power" and "motive" together.  {randomness} is an optional value for "power".
- __une interact {relationship to pc} {demeanor}__ - Runs "mood", "bearing" and "focus" together.  {relationship to pc} is an optional value for "mood".  {demeanor} is an optional value for "bearing".
- __une identity__ - Generates a 2-word description for a character.
- __une power {randomness}__ - Generates a character's power level relative to pc's power level, based on {randomness}: an optional number from 1 (order), to 5 (chaos), defaulting to 3 (standard).
- __une motive__ - Generates three 2-word descriptions for a character's motivations.
- __une mood {relationship to pc}__ - Generates a character's willingness to socialize for this interaction, based on {relationship to pc}: an optional number from 1 (love), to 7 (hate), defaulting to 4 (neutral).
- __une bearing {demeanor}__ - Generate a character's attitude for this interaction, based on {demeanor}: an optional number from 1-8, defaulting to random and meaning one of the following:
    1 - sceming       2 - insane       3 - friendly          4 - hostile
    5 - inquisitive    6 - knowing    7 - mysterious    8 - prejudiced
- __une focus__ - Generate a character's primary interest for this interaction.

***

### tejs_adventurecrafter
Shortcuts for Adventure Crafter.  Adventure Crafter is a system to create coherent story beats through randomization and tables.  You can find more info about Adventure Crafter at [wordmill games](http://wordmillgames.com/the-adventure-crafter.html).

- __reset adventurecrafter__ - Reset adventurecrafter state to defaults.
***
- __turning point__ - Get a list of five plot points to represent a major milestone in a plotline.
- __plot point__ - Get a single plot point, generated from the plot points table.
- __themes pick__ - Pick a weighted random theme, as per the Adventure Crafter rules.
- __themes__ - Show the ordered list of themes.
- __themes fill__ - Fills the remaining open theme slots with random themes.
- __themes roll__ - Fills the next open theme slot with a random theme.
- __themes add {theme id}__ - If {theme id} (an optional number from 1 to 5) is NOT included, this shortcut shows the options for {theme id}.  If {theme id} IS included, this shortcut fills the next open theme slot with the theme of {theme id}.  {theme id} can be one of these options: 1 (Action), 2 (Tension), 3 (Mystery), 4 (Social), 5 (Personal).
- __themes clear__ - Clear all theme slots.
- __ac chars gen__ - Generate a new character description, as per the Adventure Crafter rules.
- __ac chars pick__ - Pick a random char, as per the Adventure Crafter rules.
- __ac chars__ - List the character entries.
- __ac chars add {character}__ - Add the given {character} (required text) to the list of character entries.
- __ac plots dupe {character index}__ - If {character index} (an optional, positive integer) is NOT included, this shortcut shows the options for {character index}.  If {character index} IS included, this shortcut duplicates the character that is indexed by {character index}.
- __ac chars remove {character index}__ - If {character index} (an optional, positive integer) is NOT included, this shortcut shows the options for {character index}.  If {character index} IS included, this shortcut removes one entry of the character that is indexed by {character index}.
- __ac plots pick__ - Pick a random plotline, as per the Adventure Crafter rules.
- __ac plots__ - List the plotline entries.
- __ac plots add {plotline}__ - Add the given {plotline} (required text) to the list of plotline entries.
- __ac plots dupe {plotline index}__ - If {plotline index} (an optional, positive integer) is NOT included, this shortcut shows the options for {plotline index}.  If {plotline index} IS included, this shortcut duplicates the plotline that is indexed by {plotline index}.
- __ac plots remove {plotline index}__ - If {plotline index} (an optional, positive integer) is NOT included, this shortcut shows the options for {plotline index}.  If {plotline index} IS included, this shortcut removes one entry of the plotline that is indexed by {plotline index}.

***

### tejs_rpgtools
Shortcuts to help in playing tabletop rpgs, either group or solo.

- __tbl twist__ - Random table: a plot twist.  [Source](https://jvhouse.xyz/plot-twist-situations).

***

### tejs_clips
Shortcuts that let the user manage clips of text.  A "clip" is a bit of named text that can be quickly added to your note.  Similar to a shortcut, but simplistic and tied to the session state.

- __reset clips__ - Remove all clips.
- __clips__ - Lists all stored clips.
- __clips get {name}__ - Expands to the value stored in clip {name} (a required name string).
        Alternative shortcut: __cg {name}__.
- __clips add {name} {value}__ - Creates a clip named {name} (a required name string) that stores the string {value} (a required text).
- __clips expansion {name}__ - Creates a clip named {name} (a required name string) that stores the previous expansion.
- __clips remove {name}__ - Removes the clip named {name} (a required name string).

***

### tejs_arrows
Shortcuts for writing various arrows:
- ????????????
- ????????????
- ????????????
- ??????????????????
- ????????????
- ??????????????????

***

### tejs_lipsum
A decent Lorum Ipsum generator.

- __lipsum {paragraph count}__ - Generates a lorem ipsum text with {paragraph count} paragraphs.  If {paragraph count} is omitted, it defaults to 1.

***

### tejs_support
Various helper shortcuts of minimal category.

- __rngseed {seed}__ - Sets Math.random to a custom random number generator with a seed of {seed} (a non-zero integer).  Useful for testing.  If {seed} is omitted, random number generator is returned to javascript default.

***
