# Shin Megami Tensei NINE: English Translation Patch

A fan translation of *Shin Megami Tensei NINE* (Atlus, Xbox, 2002), which was only released in Japan.
The patcher turns your own copy of the Japanese game into an English one. It contains no game data: only the
differences between the original files and the translated ones.

**Status: complete translation, fully playable.** All of the game's text has a translation and has been tested, but it hasn't had a full review or a
complete playthrough of all routes yet. Expect some awkward lines, text that runs a little long in places, and the odd bug.
The version is the code in the patcher's file name and window title.

## What is translated

- **The whole story, on both routes.** Male and female protagonist routes, including the event scenes and the
  real-world scenes between dives into Idea Space.
- **Every character and NPC.** Town and district dialogue, shops, the Bureau, and Navi gossip in every district
  and voice.
- **Demon negotiation.** All 17 demon personalities, plus the special and enemy conversations.
- **Hacking battles.** The tutorials and the in-battle messages.
- **Menus and data.** Demon names, races, skills and their descriptions, items, weapons, armour and relics, status
  screens, party editing, shops, save/load, name entry and system messages.
- **Player name.** Name entry accepts English letters. The hero's full name keeps the Japanese order, surname
  first ("Azuma Kei").

**Not translated:** text that is part of a picture rather than the game's font, such as the title logo, some menu
artwork and the videos. These stay Japanese.

## Translation style

- **Meaning and voice over literal wording.** Each line is translated as part of its whole message and scene.
  Characters keep their own way of speaking: Baraki's blunt slang, Naito's polished courtesy, the Guide's
  bureaucratic politeness, Emi's childish affection, the demons' personalities.
- **Official terminology.** Demon, race, skill and item names follow the newest official Atlus English spelling
  where one exists (for example *Macca*, *Jack Frost*, *Cerberus*).
- **No honorifics.** "-san", "-kun" and the like are dropped, and the politeness they carry shows in the English
  wording instead. Emi calls the hero "Big Bro" or "Big Sis".
- **Names.** The hero's full name keeps the Japanese order, "Azuma Kei". Japanese names and places are kept in Hepburn
  romanisation, without macrons.
- **Setting kept as it is.** The game's 2002 vision of a networked Tokyo, its places and its culture aren't
  localised away. Emoticons stay as ASCII, for example `(^_^;)`.
- **Real-world scenes** use the game's own "Name: line" layout, with continuation lines indented under the text.
- **Readable on screen.** The game normally draws English letters as fixed-width characters. The patch adds a
  proportional font, and squeezes a label slightly when it's wider than its menu slot. When a translation needs
  more room than the Japanese had, a message box can get an extra line or page.

## What you need

- **Your own dump of the Japanese disc**, *Shin Megami Tensei NINE* (Japan, AT-002). The patcher checks every
  file against the known-good Redump dump of that disc and refuses anything else, so a wrong, modified or
  already-patched copy is never damaged. The 2003 Platinum Collection reprint hasn't been verified; if its files
  differ, the patcher will tell you.
- **Windows 10 or 11, 64-bit.** Nothing else to install: the patcher is a single exe with everything built in.
- **Free disk space** on the drive where you save the result: about 5 GB for ISO or folder output, and about 7 GB
  when the input or output is CSO or CCI. The temporary files are deleted afterwards.

### Accepted input

| Format | Notes |
|---|---|
| ISO, full Redump image | about 7.3 GB, including the video partition |
| ISO, trimmed (xiso) | for example a dump made with extract-xiso or Repackinator |
| CSO | Stellar / MakeMHz format; split files `name.1.cso` + `name.2.cso` work, pick either one |
| CCI | Cerbios / Repackinator format; split files `name.1.cci`, `name.2.cci`... work, pick any one |
| Extracted folder | the folder that contains `default.xbe` |

A copy that has been "scrubbed" or repacked with files removed or changed can't be patched. Use a complete dump.

### Output formats

| Format | Use it for |
|---|---|
| ISO | xemu, burning to DVD, or loaders on a modded Xbox |
| CSO | Stellar and Cerbios loaders (written as `name.1.cso`) |
| CCI | Cerbios and Repackinator |
| Folder | copying to the Xbox hard drive (for example with FTP) and launching `default.xbe` |

## How to patch

1. Run `SMT9_EN_Patcher_<version>.exe`.
2. **Japanese game:** click **File...** and pick your ISO, CSO or CCI, or click **Folder...** for an extracted
   game.
3. **Output format:** choose ISO, CSO, CCI or Folder.
4. **English game:** keep the suggested name, or click **Browse...** to choose your own.
5. Click **Patch**. It takes a few minutes, and longer for CSO or CCI. The window shows each step and ends with
   "Done".

Your original files are never changed.

### Command line

```
SMT9_EN_Patcher_<version>.exe <japanese game> [<output>] [--format iso|cso|cci|folder]
```

The output format follows the output's extension (`.iso`, `.cso` or `.cci`, or no extension for a folder),
unless you give `--format`. The exit code is 0 on success and 1 on failure.

Examples:

```
SMT9_EN_Patcher_<version>.exe "SMT NINE (Japan).iso"
SMT9_EN_Patcher_<version>.exe "SMT NINE (Japan).1.cso" "SMT NINE (English).cci"
SMT9_EN_Patcher_<version>.exe "D:\Games\SMT NINE" "D:\Games\SMT NINE (English)" --format folder
```

## Playing

- **xemu:** load the English ISO. Stock xemu releases have rendering glitches in this game whether or not it's
  patched: a corrupted title screen, and speckled or garbled text box backgrounds in Idea Space. These are xemu
  emulation bugs (xemu issues #1326 and #2276), not problems with the patch.
- **Original Xbox:** use the ISO, CSO or CCI with your loader, or copy the folder to the hard drive.
- **If you played the Japanese game before on the same Xbox or xemu hard disk:** the game keeps some files in its
  hard disk cache. The patch already ships its font under a new name so the old cached copy isn't used, so no
  cache clearing is needed.

## Troubleshooting

| Message | Meaning |
|---|---|
| *... does not match the Japanese release this patch expects* | The input isn't an unmodified Japanese dump: it's a different release, already patched, scrubbed or repacked. |
| *Not enough free space* | Free up space on the output drive, or choose another drive. |
| *is not a readable CSO/CCI image* | The compressed file is damaged or incomplete. With split files, make sure every part is in the same folder. |
| *No default.xbe found* | The file or folder isn't an Xbox game, or you picked the wrong folder. |

## Credits and licences

- Translation, tools and patcher: the SMT NINE English translation project.
- Script extraction builds on smt-nine-tools by RayCharlizard (MIT licence).
- The patcher includes extract-xiso (XboxDev, its licence is bundled) and uses the LZ4 (BSD) and bsdiff4 (BSD)
  libraries.
- *Shin Megami Tensei* and *Shin Megami Tensei NINE* are trademarks of Atlus/SEGA. This is an unofficial fan
  project, not affiliated with them. It contains no game data; you need your own copy of the game.
