# ProgramISO
ProgramISO is a XKB layout, inspired by [QWERkey](https://github.com/MicahElliott/QWERkey/), designed specifically for programming on an ISO 105-keys keyboard with minimized reach.
The keyboard layout is based on QWERTY-US but brings special keys (enter, control, ...) and symbols (#, %, ...) closer to the home row thanks to layers and dual-role keys.

![Preview of the ProgramISO keyboard layout on the alphanumeric block of a typical ISO keyboard in black](/pictures/keyboard-layout-alphanumeric.png)
![legend](/pictures/legend.png)

## Brief explanation on layers and dual-role keys
The character that gets produced on the computer not only depends on the physical key being pressed but also on the current active layer. The most familiar use of layers is that of non-shifted vs shifted. On a classic QWERTY keyboard, pressing the first key normally produces `q` but if you hold shift and press that same key, `Q` gets produced. This means that the classic QWERTY keyboard layout maps the first key to `q` when on the first layer/level and to `Q` when the second layer/level is active. As already mentioned, one way to access this second level is to hold shift but one can also use caps lock whose behaviour is different. The XKB protocol defines 3 ways to access a certain level:
1. **Switch** : Level X is active as long as this switch is held. Familiar Examples: Shift, AltGr.
2. **Lock** : Level X is activated when the lock key is pressed and remains active until the lock key is pressed again. Familiar Examples: Caps Lock, Num Lock.
3. **Latch** : Pressing (and releasing) the latch key only applies Level X to the next pressed key before going back to default layer. Familiar Examples: Sadly none.

It's rather unfortunate to observe that latching is so uncommon since [key sequences are more ergonomic than key chords](http://xahlee.info/kbd/banish_key_chords.html) and you might be glad to hear that ProgramISO does make use of latch keys but only for one modifier key while all others are switches. Why? The answer lies in dual-role keys.

You see, one of the untapped potential of switch modifiers is that they don't do anything useful when they're tapped (i.e. pressed and released on its own) but thanks to programs like [xcape](https://github.com/alols/xcape), we can turn these switch modifiers into dual-role keys which act as modifiers when held but act as other keys when tapped. This allows us to make more with less.

## Special keys

| QWERTY | Hold | Level 1 | Level 2 | Level 3 | Level 4 |
|--------|:----:|---------|---------|---------|---------|
| <kbd>Tab</kbd>    | Level3 Switch | Tab | Left-Tab | ~ | Tab | 
| <kbd>[</kbd>      | × | Backspace | Backspace | [ | Backspace |
| <kbd>]</kbd>      | × | Delete | Delete | ] | Delete |
| <kbd>Caps Lock</kbd> | × | Escape | Escape | : | ; |
| <kbd>;</kbd> | Control | Enter | Enter | Enter | Enter |
| <kbd>Left Shift</kbd> | Control | Control | Control | Control | Control |
| <kbd>\\</kbd> | Shift | \ | \| | \ | \| |
| <kbd>/</kbd> | Shift | / | ? | / | ? |
| <kbd>Right Shift</kbd> | × | Compose | Compose | Compose | Compose |
| <kbd>Left Control</kbd> | Hyper | Hyper | Hyper | Hyper | Hyper |
| <kbd>Space</kbd> | × | Space | - | _ | Space |
| <kbd>AltGr</kbd> | Level3 Switch | Level3 Latch | Level3 Latch | Level3 Latch | Level3 Latch |

## Design Philosophy & Mnemonics
#### Number row
If you use an ISO keyboard, that's probably because you live in Europe and if that's the case, chances are also high that you need to input accented characters. Using the compose key for each accented character gets annoying if your language uses accents a lot. I speak French so I added french accented characters on Level3 of the number row, in a fashion that is lightly inspired by classic French and Belgian keyboard layouts.

The two leftmost keys on the number row hold `â` and `à` because the normal letter `A` is also the leftmost on the home row (it is also the leftmost in AZERTY). The tilde key is somewhat hard to reach but still feasible so I've placed the uncommon `â` there while `à` is much more commonly used so it is placed on the easier to reach <kbd>1</kbd> key.

The `é` found on AZERTY remains at the same place, though on Level3. The two next keys (key <kbd>3</kbd> and key <kbd>4</kbd>) are all adjacent to the normal letter <kbd>E</kbd> so they're used to input accented e's.

On AZERTY, key <kbd>5</kbd> is used to enter `(` which looks like a 'C' so this is where you'll find `ç`.

Key <kbd>6</kbd> is a pain to reach so I did not add any accented characters there.

Keys <kbd>7</kbd> and key <kbd>8</kbd> are both adjacent to the normal letter <kbd>U</kbd> so they're used to input accented u's. On AZERTY, key <kbd>7</kbd> is used to input `è` which is an e with a *grave* accent but since it made more sense to pack all accented e's together, that key is free to be used for accented u's. Since key <kbd>7</kbd> inputs *grave* accent in AZERTY, I deciced it would be a good fit for u with a *grave* accent in ProgramISO. 

Key <kbd>9</kbd> is close to <kbd>I</kbd> so this is where you'll find `î`.

Key <kbd>0</kbd> is close to <kbd>O</kbd> *and* 0 looks like an 'O' so this is where you'll find `ô`.

The last two keys are useful if you'd rather get square brackets by a single key press. It also contains « *fancy* » quotes and the degree sign `°` at the exact same place as in AZERTY. I often make bullet points so it's nice to have a fancy bullet point for these purposes `•`.

#### Upper row
All symbols from the tilde key to the <kbd>8</kbd> key are translated one key down and available on level 3. For example, Level3 <kbd>Q</kbd> produces `!` because it is situated right under the <kbd>1</kbd>/<kbd>!</kbd> key and level3 <kbd>U</kbd> produces `&` because it is right under the <kbd>7</kbd>/<kbd>&</kbd> key.

QWERTY's <kbd>=</kbd>/<kbd>+</kbd> key gets spread out over Level3 <kbd>O</kbd> and Level3 <kbd>P</kbd> (for **P**lus) which helps to keep them close to each other.

The bracket keys still keep the square brackets on Level3 but become backspace and delete on Level1 and Level2. You can see it as the backspace staying in the same corner but closer to the home row with the left half used for deleting characters to the left and the right half for deleting characters to the right.

#### Home row
<kbd>Caps Lock</kbd> essentially becomes the Vim key. It's an escape key which can also produce colon (very handy for quickly entering Ex mode from insert mode). The added semicolon on Level4 is simply to stay faithful to the QWERTY layout, the semicolon on Level1 of the rightmost key of the home row is personally more convenient for me. People commonly turn <kbd>Caps Lock</kbd> into a dual-role key for both `Control` and `Escape` but this is annoying if you quickly change modes in Vim. When I experimented with this, I kept accidently hitting <C-some_key> when I just wanted to quickly go back to Normal mode and use normal mode commands.

Putting Home on Level3 <kbd>A</kbd> kinda goes against Vim's append command but imagine it this way: Your left fingers resting on the home row represent a line. The beginning of this line aka the home is at the pinky while the end of the line is at the index. The same reasoning applies for Level3 <kbd>F</kbd>.

<kbd>S</kbd> and <kbd>D</kbd> are between 2 navigation commands (`Home` and `End`), thus it makes sense for them to also be navigation commands.
Level3 <kbd>S</kbd> is `Page Down` because the letter 's' is written from top to bottom. The pen goes *down* when writing this letter (There are probably some people out there who write 's' from bottom to top but I have yet to encounter one).
Level3 <kbd>D</kbd> is `Page Up` because the letter 'd' has a stem pointing *up* (which is called an "ascender" in typography).

Level3 <kbd>G</kbd> is `Volume Up` because it's above the <kbd>V</kbd> key which is used as `Volume Down` since the letter 'v' points down.

<kbd>H</kbd><kbd>J</kbd><kbd>K</kbd><kbd>L</kbd> are the Vim arrow keys and now you can use them everywhere if you are on Level3! You can also get the arrow drawings (← ↓ ↑ →) on Level4. If you use keyboard shortcuts requiring <kbd>Shift</kbd>+<kbd>Left</kbd>,<kbd>Right</kbd>,... I recommend replacing the arrow drawings on Level4.

The pinky's resting state can now be used to input `enter`/`return` and be used as a `control` modifier. I don't have a mnemonic for this but it's the best feature of the keyboard layout so you shouldn't have issue remembering it ;)

The backtick joins its siblings on the Level3 of the <kbd>'"</kbd> key.

In C-like languages, there is often a semicolon at the far-right of a line. Such is also the case for the home row of this keyboard layout. Additionally, the semicolon, which often precedes a new line, is right next to the big fat enter key so you can just roll your pinky over these two keys to end a statement and move on to the next.

#### Lower row
Both shifts are moved one key closer, firstly because they're used a lot and secondly because it allows us to move other modifiers closer to the home row. This is where we'll be able to take profit of the ISO keyboard layout. As opposed to an ANSI or a JIS keyboard layout, the ISO keyboard layout, common in Europe, has a shorter left shift key to accommodate the extra key. Normally, this kinda sucks because it requires extra stretch for the pinky to reach a very commonly used modifier. However, if we remap the extra key to `shift` (that extra key was redundant anyways, it's useful for some national European layouts but not on QWERTY-US), we can remap the original left shift to `control`. This is fantastic because `control`, `shift`, `z`, `x`, `c`, and `v` are now all on one neat row! No need to rotate the wrists in order to use these very common key shortcuts now. Additionally, ProgramISO's right shift is vertically aligned with ProgramISO's right control (which doubles as the enter key), meaning you can form a guitar-like pinky barré to hit both control and shift with one single finger without leaving the home row!

Level3 <kbd>V</kbd> is for **V**olume Down because it is the first letter of volume and looks like a down arrow.

Level3 <kbd><</kbd> and <kbd>></kbd> produce {curly brackets} because these keys are aligned with the <kbd>9</kbd>/<kbd>(</kbd> and <kbd>0</kbd>/<kbd>)</kbd> keys and if you do the fusion: `(` + `<` = `{` and `)` + `>` = `}`.

#### Lowest row
The original left control is not required anymore as ProgramISO moved it one key higher so it's been remapped to Hyper to unlock a whole new extra layer of keyboard shortcuts that won't conflict with any program's key shortcuts since they never make use of the Hyper modifier.

<kbd>Spacebar</kbd>, the most easy to reach key, is finally given a little extra work. Pressing Level2 <kbd>Spacebar</kbd> produces `-` because it is often used in place of spaces. Hyphen is placed on Level2 because Level2 refers to *upper*case and hyphen is positioned higher than the underscore which can be found on Level3. Underscore is placed on Level3 <kbd>spacebar</kbd> because it is also frequently used as pseudo-spaces. It is important that underscore is easier to type than hyphen because, as it turns out, underscore is the most commonly used symbol in many programming languages. 

![Punctuations frequency in all languages](http://xahlee.info/comp/i/computer_language_char_frequency.png)

ProgramISO makes it very easy to use your two strongest fingers (i.e. the thumbs) to input `_`. Simply press or hold <kbd>AltGr</kbd> with your right thumb and press the <kbd>spacebar</kbd> with the left thumb.

## Breaking Changes from QWERTY
ProgramISO tries to deviate minimally from classic QWERTY-US and, generally, merely adds more functionality to each key without altering its classic behaviour but there are still some breaking changes being introduced (for the better). The keys that got radically changed are highlighted in red in this picture:
![Highlighting of the breaking changes in red](/pictures/keyboard-layout-breaking-changes.png)
