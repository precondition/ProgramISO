# Ideas that may or may not get added to ProgramISO

* Put french accented characters in a variant
* Put dead accents in another variant
* Variant where the first 2 levels of the number row are reversed (Afterthought: The number row is notoriously hard to touch type on. Adding the frequently used symbols on the upper row but on a layer still is more convenient than being able to access the symbols on Level 1 of the number row)
* Variant(?) with a 5th level set as a Latch on <kbd>R-Shift</kbd> key to access accented characters like on my old unreleased prototype kb layouts. (Physical <kbd>Ctrl</kbd> key(s) can be used to regain lost compose key. Same can be said for the menu key)
* ~~Level3 M-Enter-Ctrl key could hold ;~~ **Added to ProgramISO**
* Remap <kbd>Menu</kbd> or <kbd>L-Ctrl</kbd> to be a combination of modifiers (e.g. Ctrl+Shift or Ctrl+Level3) in an effort to reduce finger gymnastics.
* Opening a new branch for more extreme modifications, where minimizing deviations from stock QWERTY is no longer a preoccupation
* **Numpad**
    * Possibly add a numpad centered on 'K' on a layer? This would require a switch because latch would be too impractical for entering digit**s**. A lock could be considered but I believe it would be overkill to use a lock just for numbers.
    * If we assume that a numpad layer is added, we can turn level1 number row into a bunch of level/layers latches
    * If numpad is centered on <kbd>K</kbd>, <kbd>AltGr</kbd> could be used as `0`. (The spacebar could also be used but that's a bad candidate because I might need to input spaces between triplets of digits)
    * Centering the numpad on <kbd>I</kbd> instead could also be interesting. Why? Familiarity. 7, 8, 9 do not move and neither do the comma and the dot which are often used in number entry. If numpad is centered on K, commas and dots will be harder to input.
    * Numbers are often used for indexing so it would be a good idea to add a colon at its classic QWERTY position on the numpad layer. For the same reasons, adding square brackets on e.g.<kbd>P</kbd> and<kbd>/</kbd> could also prove to be useful.
    * Access numpad layer (possibly use Mode_switch since we're kinda running out of layers on the ProgramISO layout) with <kbd>LCTL</kbd> and use the rightmost home row key as Compose.
* xcape can also be used to dual-role a level X switch and a level Y latch on the same key
* I don't use PgUp and PgDn a lot and yet they occupy the home row. <kbd>S</kbd> and <kbd>D</kbd> could instead yield openers and closers (i.e. parens and brackets) on certain layers
* Move accents away from Level 3 number row and add square brackets `[]` on level 3 of <kbd>9(</kbd> and <kbd>0)</kbd>
* Shift+Escape i.e. Level 2 <kbd>Caps Lock</kbd> is hardly used. It could be replaced with something more useful like a latch or something. The colon is very convenient at Level3 since it can be accessed with a pinky barré between <kbd>Tab</kbd> and <kbd>Caps Lock</kbd>.
* Remap <kbd>Spacebar</kbd> to be a Level Y switch on a certain level X which can be accessed with a Level X latch. As such I can dual-role all modifiers of the bottom row into latches which I can combo with non repeated keysyms or combo with space as a switch + repeated keysym. By combining lvlX latch and lvlY switch on space, this makes it easier to access lvls >5.
* A better analysis of keysyms that are used continuously (e.g. obvious ones like `Left` but also less obvious ones like `{` stemming from my use of vim) and keysyms that don't get repeated (e.g. accented characters, `âscîîcîrcum`, `$`, ...) is needeed in order to better understand what keysyms would benefit from *switches* and add non-repeated keysyms on a layer that is accessed with a *latch*.

| Keysyms non-repeated | Keysyms repeated 2-3 times | Keysyms repeated >3 times |
|:--------------------:|:--------------------------:|:-------------------------:|
| ~ accents ! @ # $ %  | ` @ ! # & * = + / { } < >  | Tab Bckspce Del PgUp PgDn |
| ^ ( ) [ ] ° « • »    | - _ [1;9] "                | VolUp VolDn Left Down Up  |
| Home End ; ' : | \ , |                            | Right 0                   |
| Compose Enter Escape |                            |                           |
| Menu Insert PrtSc    |                            |                           |
| ScrLk F[1;12]        |                            |                           |

* Use DreymaR's xkb colemak files as a new basis for ProgramISO, adding, editing and removing as necessary. The idea isn't to take keyboard layout inspiration from dreymar's colemak but to fetch the magic bits that give dreymar's colemak superpowers
* Create a navigation layer where <kbd>H</kbd><kbd>J</kbd><kbd>K</kbd><kbd>L</kbd> are normal cursor movements like in Vim but the keys above (<kbd>Y</kbd><kbd>U</kbd><kbd>I</kbd><kbd>O</kbd>) are Ctrl+Mvmnt and keys below (<kbd>N</kbd><kbd>M</kbd><kbd>\<</kbd><kbd>\></kbd>) are Shift+Mvmnt. Something similar can be made for the left hand in regards to `Home`, `PgDn`, `PgUp`, and `End`.
* ~~Assign bigrams and trigrams to keys or key combos, possibly with the use of an Hyper key on <kbd>Ctl_L</kbd> (Stock QWERTY position) or as a dual-role on a number row key.~~ ~~Added to ProgramISO on the number row because the lower corners of the keyboards are harder to reach than the upper corners~~ Removed in favor of the next idea
    * Chording is hard. Alternatively I could set a very uncommon symbol at level1 of a key and use text expansion software such as Autokey to expand {weird symbol}{letter} and {letter}{weird symbol}
* Mod tap the Level 2 of the spacebar.
* There are way too many ways to enter `[]`. I should remove some.
* Level 3 <kbd>B</kbd> to do `Ctrl+←` (like in Vim) and <kbd>N</kbd> to do `Ctrl+→`.


# Interesting resources
* There are so many obscure things that are possible with xkb like those briefly mentionned in this article : https://medium.com/@benreaves/keybinding-in-groups-for-linux-938f379648cb but I can't seem to find documentation which lists and explains all those options. [This man page](https://www.systutorials.com/docs/linux/man/3-XkbKeyTypesForCoreSymbols/) is a good start.
* [Kinto](https://github.com/rbreaves/kinto) is doing some funky xkb stuff that could be interesting.
* [This project](https://gitlab.com/wsha/chorded_keymap) is an interesting concept. Not sure if it's feasible with xcape but using <kbd>F</kbd> and <kbd>S</kbd> as the chord has some potential (It's better than the default <kbd>D</kbd> and <kbd>S</kbd>, which frequently come together: e.g. "towar**ds**", ...)
* https://unix.stackexchange.com/questions/302163/how-to-make-a-iso-level4-shift-and-lock-in-xkb/412599#412599
* https://hack.org/mc/writings/xkb.html
* https://github.com/xkbcommon/libxkbcommon
* https://github.com/DreymaR/BigBagKbdTrixXKB/ : This one is of particular interest since it also uses XKB for advanced layer configuration
* [KMonad is a keyboard remapping utility written to provide functionality that aligns with that provided by the amazing QMK firmware.](https://github.com/david-janssen/kmonad)
* [This reddit post](https://www.reddit.com/r/MechanicalKeyboards/comments/fwu1tc/this_is_my_southpaw_corsair_seaform_a_k70_mk1/) contains a gif of pinky-barré.
