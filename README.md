# Reduxibox Suite

Play your original Xbox (2001) games natively on Linux.

Reduxibox Suite is a compatibility layer, like Wine and Proton are for
Windows programs. It runs an Xbox game's own code directly on your
computer's processor, stands in for the Xbox's kernel, and provides the
hardware the game talks to: the graphics chip (drawn with Vulkan), the
sound processor and the controllers.

It installs as two programs:

- **Reduxibox** plays games.
- **Reduxibox Game Converter** turns your game discs, as ISO or XISO disc
  images, into `.msxbx` games that Reduxibox plays.

Reduxibox Suite includes no games and no Microsoft or Xbox software,
BIOS, kernel or keys. You need your own legally obtained games.

**This project is not for piracy.** It's built so that you can keep
enjoying the Xbox games you bought. It was born from Microsoft slow-walking
support for original Xbox games.

## Download

Get the latest version from the
[Releases page](../../releases/latest): the installer
(`Reduxibox-Suite-<version>-x86_64.run`), its signature (`.run.asc`) and
the public key (`reduxibox-signing-key.asc`). Download all three into the
same folder.

**Read the release notes for the version you download.** They have that
version's install steps, what changed, and what's known not to work yet.
Some instructions change as the project moves on.

### What you need

- A 64-bit PC with Linux: Debian 12 or newer, Ubuntu 24.04 or newer
  (Linux Mint 22 or newer), Fedora 43 or newer, or an up-to-date rolling
  release such as Arch Linux.
- Graphics with Vulkan 1.3 and up-to-date drivers.
- An X11 or Wayland desktop, with PipeWire or PulseAudio for sound.

### Install

Open a terminal in the folder with the three files and run the installer
(replace `<version>` with the version you downloaded):

```bash
sh Reduxibox-Suite-<version>-x86_64.run
```

It checks its own signature before installing anything, asks for your
password, and offers to install anything your system is missing.

### Check the download

The installer is signed by Reduximus Technologies. To check it yourself:

```bash
gpg --import reduxibox-signing-key.asc
gpg --verify Reduxibox-Suite-<version>-x86_64.run.asc Reduxibox-Suite-<version>-x86_64.run
```

It must say **Good signature**, with this key fingerprint:

```
751F F470 38CA 06E6 0804  B16F F996 3C9A A78D 927C
```

If it says **BAD signature** or shows a different fingerprint, delete the
file and don't run it. Only download Reduxibox Suite from this
repository's releases.

## Games

As of October 15, 2026 (version 0.3.4.1), measured on an AMD Ryzen 7
5700U laptop with its built-in graphics.

### Playable

These run at full speed (or at the game's own frame-rate limit), with
sound, as far as they've been tested.

| Game | Tested to | Speed |
| --- | --- | --- |
| Halo: Combat Evolved | The first mission | 30 fps (the game's own limit) |
| Halo 2 | The opening training | 28–30 fps (the game's own limit is 30) |
| The Lord of the Rings: The Return of the King | Combat in the first level | 30 fps (the game's own limit) |
| MVP Baseball 2004 | Pitching, batting and fielding | 55–60 fps |
| Crazy Taxi 3: High Roller | Driving and picking up customers | About 60 fps |
| X-Men Legends | Opening gameplay | About 48 fps |
| X-Men Legends II: Rise of Apocalypse | Opening gameplay | About 31 fps |
| The Punisher | The first mission | About 30 fps |
| The Chronicles of Riddick: Escape from Butcher Bay | The first level | 30–45 fps |
| Voodoo Vince | The opening story | 30 fps (the game's own limit) |
| Fatal Frame | Exploring the first rooms | 60 fps |
| Fatal Frame II: Crimson Butterfly | The opening forest | 30 fps (the game's own limit) |
| Ultra Bust-A-Move | Matches | 60 fps |

### Nearly there

| Game | Where it stands |
| --- | --- |
| True Crime: Streets of LA | Playable; 26–30 fps in the city, against the game's own limit of 30 |
| NBA Jam 2004 | Playable; matches run at about 25–50 fps and sometimes drop below 30 |
| Battlefield 2: Modern Combat | Reaches the campaign menus; not yet tested in a mission |
| Steel Battalion | The first mission, with the cockpit on a gamepad and keyboard, or with the real Steel Battalion controller through an Xbox-to-USB adapter (not yet tried with real hardware); slow in missions |
| Project Gotham Racing | Not ready yet: its sound stops after a few seconds |

No game has been played from start to finish yet, and saving and loading
haven't been checked. Other games haven't been tested yet.

## Help the list grow

Play your own games on Reduxibox Suite and tell us how they do.

- **A game works:** email **reduximusgaming@gmail.com** with the game's
  name and how far you got.
- **A game has problems:** take a screenshot of the problem and message
  **@Reduximus_Maximus** on Discord, or open an [issue](../../issues).
  Include your Linux distribution and graphics, and the log of the run:
  `~/.local/state/xbox-compat-layer/logs/last-run.log`.

## Legal

Xbox is a trademark of Microsoft Corporation. Reduxibox Suite is not
affiliated with or endorsed by Microsoft. Game titles are trademarks of
their respective owners.

Have fun!
