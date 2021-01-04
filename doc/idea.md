# purpose

- experiment with tilemaps and procedural maze generation and
  online multiplayer
- finally get the "Vim tutor" idea off my chest

# aesthetics

- isometric tilemap
- black background
- tiles are drawn in grid wireframe style
    - each tile contains about 10 grid divisions
    - grid line color transitions to black towards bottom of
      tile, makes it look like tile bottoms "vanish"
- wizard mostly looks like a giant cloak
    - can just barely see a hand holding a staff and just barely
      see some feet under the cloak
    - prominent feature is the staff
    - top of staff glows with color to indicate player
- replicate Vim stuff:
    - display key's pressed in lower right
    - support a `.vimrc`
    - `:` starts command line
    - `/` starts search

# play

- number of goals in each level increase as player learns what to
  do
- in the beginning, player just needs to exit the maze
    - exit the maze
    - level 1 is just walk your way out of the maze
- level 2 contains missing tiles that the player must teleport
  past
- level 3 encourages a preference for "rapid" movement over h,j,k,l
    - looks exactly like level 1, but the tiles behind the player
      are "vanishing" faster than the player can walk
    - player must use teleportation to get out before floor falls
      away
- level 4, maze contains trophy runes the player must read to
  uncover the exit
- level 5, player must "mark" tiles to connect certain trophy
  runes, the exit appears at the center of these runes, only
  visible to the player that makes the exit appear
    - when playing opponents, marking tiles is how wizards
      battle:
    - you can try to "type" faster, erasing marks and laying down
      your own marks
    - you can also cast spells against your opponent
    - spell casting is something players gain with experience and
      is not tracked by the game: the player "remembers" the name
      and the usage of the spells and types them accordingly with
      `:`
    - of course the spell `:h` opens help which is ridiculously
      long documentation for everything, including the spells,
      and `:h blah` jumps to help for blah and `:h :blah` jumps
      to help for spell `blah`
    - attacking an opponent with a spell buys time to mark the
      tiles and make the exit

- player must trace all the trophy runes to make the exit visible
  to the player
- some runes 
- player 

- wizard walks around the maze with VI controls:
    - `h,j,k,l`
- wizard teleports:
    - proceed walk with number to move that amount
    - use `b` or `w` to go back or forward to next spot in maze
      where there is a "choice"
    - use `$` to go as far as possible forward
    - use `0` to go as far as possible backward
    - use `fr` to find next rune going forward
    - use `Fr` to find next rune going backward
- wizard interacts with runes:
    - `K` shows what the rune is: trap/trophy/spell
        - if it's a spell, more info is displayed
        - `q` to quit info display, or `tab` to keep reading
        - it's up to the player to remember spell names and how
          to use them
    - `i` to start interacting
    - `Esc` exits interaction mode
    - while interacting, user types
    - what is typed appears above the wizard's head until enter
      is pressed
    - enter on a blank line causes wizard to tap the tile,
      changing it to the wizard's wand color -- this gives the
      wizard a way to "mark" a tile
    - When not in interactive mode, hitting `x` removes the
      "mark" (tile goes back to its original color) -- player can
      also `x` opponents markings
    - similarly, `dd` removes all marks along the maze corridor,
      whether the player's own or the opponents
      `dw` and `db` remove forward and back to next blah, you get
      the idea
    - instead of typing entire word, Ctrl+X, Ctrl+N or Ctrl+X,
      Ctrl+P starts throwing in words (and continued pressing
      Ctrl+N or Ctrl+P cycles through the pop-up of words)
    - the words for interaction are already "there" (player just
      can't see them), as if this was a text file opened in Vim
      and it already had these words in it
    - gameplay here is that the maze has runes in the tiles,
    - runes are trophies and traps
    - player has to "trace" all trophy runes to open the maze
      exit
        - exit opening is only shown on the player's screen
    - player is killed if player "traces" a trap rune
- wizard "shows" things on the maze:
    - `/` followed by name of thing
    - `up-arrow/down-arrow` cycle through a history of things the
      wizard has looked for in this level
    - while typing, things will highlight
    - press Enter and they stay highlighted
    - now `n` teleports wizard to the next thing "down-and-right"
      of wizard's location, and `N` to the next thing
      "up-and-left" of wizard's location
    - Cast `:noh` to turn off highlighting
    - Or hit `Esc` instead of Enter and `/` mode exits and
      highlighting is removed

# level names

Bible names are awesome, plus there's the cryptic biblical
versions of names: "Idumi" transliterates to "jdwmj" translates to
"Edom"

Ancient sculptures of biblical gods/goddesses are also good
inspiration for character artwork

https://en.wikipedia.org/wiki/Rehoboth_(Bible)

- Rehoboth
- Edom (means red -- maybe the wizard with a red staff is the
  Edomite)
- Levant
- Valley of Salt (level 2)
- Incense Route (level 1)
