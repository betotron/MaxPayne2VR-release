# Max Payne 2 VR

**Native virtual reality for *Max Payne 2: The Fall of Max Payne* (2003).**
Real stereoscopy, head tracking, motion controllers, and aiming with your hand.

> 🇪🇸 **[Versión en español aquí](README.md)**

> Mod created by **betotron** — [github.com/betotron](https://github.com/betotron)
> Powered by **[techbuzzo.com](https://techbuzzo.com)**

---

## What this is

This is not a floating screen inside your headset. The game is rendered **twice, once per eye**,
with the engine's own camera driven by your head. You turn your head and the world stays put; you
point your hand and the gun goes where you point; you take a step and Max takes a step.

| | |
|---|---|
| Real stereoscopy | yes, two views per frame |
| Head tracking | yes, rotation and position (6 degrees of freedom) |
| Hand aiming | yes |
| Game menu with the controllers | yes |
| Health and ammo panel in world space | yes |
| Cutscenes and graphic novels | on a floating flat screen |

---

## Before you start: what you need

| | |
|---|---|
| **Max Payne 2** | the Steam or GOG version |
| **DXVK** | `d3d8.dll` / `d3d9.dll` inside the game folder. The **Payne Evolution** build already ships them |
| **A headset with a 32-bit OpenXR runtime** | see the table below — **this matters** |
| **Up-to-date GPU drivers** | the mod uses Vulkan, which ships with your driver |

### ⚠️ Which VR runtime works, and which does not

Max Payne 2 is a **32-bit** program (it's from 2003). A 32-bit program **can only use a 32-bit
OpenXR runtime**. That rules out a very popular one:

| runtime | works? | why |
|---|---|---|
| **Virtual Desktop** | ✅ **Yes — this is what it was built and tested on** | installs `virtualdesktop-openxr-32.json` |
| **Oculus / Meta Link and Air Link** | ⚠️ **Should** — untested | installs `oculus_openxr_32.json`, which is 32-bit |
| **SteamVR** | ❌ **No** | it only installs `steamxr_win64.json`. **There is no 32-bit runtime**, so a 32-bit game cannot use it. This is not a limitation of the mod |

**Bottom line: use Virtual Desktop.** It is the only one tested end to end, on a **Meta Quest 3**.

---

## Installation

### Step 1 · Download the files

Download this repository (green **Code** button → **Download ZIP**) and unzip it.

### Step 2 · Open the game folder

In Steam: right-click *Max Payne 2* → **Manage** → **Browse local files**.

It's the folder that contains `MaxPayne2.exe`.

### Step 3 · Copy the TWO files

> ### ⚠️ The single most important thing in this guide
> **Do NOT copy the `mod` folder.** Copy **the two files inside it**, and drop them loose
> **next to `MaxPayne2.exe`**.

**What you downloaded:**

```
MaxPayne2VR-release/
├── mod/
│   ├── winmm.dll            <- THIS ONE
│   └── MaxPayne2VR.ini      <- AND THIS ONE
├── README.md
└── LICENCIAS.txt
```

**How the game folder has to end up:**

```
Max Payne 2 The Fall of Max Payne/
├── MaxPayne2.exe
├── d3d8.dll                 <- from DXVK, already there
├── d3d9.dll                 <- from DXVK, already there
├── winmm.dll                <- ✅ YOU ADDED THIS
├── MaxPayne2VR.ini          <- ✅ AND THIS
└── ...
```

❌ **Wrong:** `Max Payne 2\mod\winmm.dll`
✅ **Right:** `Max Payne 2\winmm.dll`

### Step 4 · Set up the game launcher — **do not skip this**

When you start the game, a small launcher window opens first. **What you pick there decides how
sharp everything looks inside the headset.**

| option | what to pick |
|---|---|
| **Graphics adapter** | your GPU (not the integrated one) |
| **Resolution** | **the highest one in the list**, ending in **× 32** |
| **Acceleration** | **D3D Hardware T&L** |

**Why it matters so much:** the mod takes the image the game renders and stretches it to the size
the headset asks for. A Quest 3 asks for **2112 × 2304 per eye**. If you leave the game at
800 × 600, that image gets stretched almost three times and looks blurry. **The launcher
resolution is the quality you will see.**

On a reference machine the list goes up to **2715 × 1527 × 32**. Yours may differ — **always pick
the last entry in the list.**

### Step 5 · Put the headset on and play

1. Start **Virtual Desktop** and connect the headset.
2. Launch Max Payne 2 **as usual**.
3. The mod loads itself. There is nothing else to run.

---

## The first time

- **Stand in a T-pose** (both arms straight out to the sides) for a couple of seconds during the
  first few minutes. The mod measures your arm on its own and saves it. **You don't press
  anything.**
- If you feel taller or shorter than the characters in the game, change `camara_altura_ojos` in
  the `.ini`. **You can do it with the game running:** save the file and it applies itself.

---

## Controls — Meta Quest 3

With Touch Plus controllers. **Your head turns the camera**, which leaves the right stick free.

### Right controller

| button | what it does |
|---|---|
| 🔫 **Trigger** | **Fire**. With the weapon wheel open, **confirms the weapon** |
| ✊ **Grip** (side) | **Use / interact** (doors, objects) |
| **A** | **Reload** |
| **B** | **Jump** |
| 🕹️ **Stick click** | **Painkiller** |
| 🕹️ **Stick** | nothing — you turn with your head |
| ✋ **Aim** | the gun points **where your hand points** |

### Left controller

| button | what it does |
|---|---|
| 🕹️ **Stick** | **Walk** (forward, back and strafe) |
| ✊ **Grip** (side) | **Melee attack** |
| **X** | **Bullet time** (slow motion) |
| **Y** | **Weapon selector** — each press steps to the next; the right trigger confirms |
| ☰ **Menu button** | **Open and close the game menu** (acts as `ESC`) |

### Inside the game menu

| | |
|---|---|
| 🕹️ **Left stick** | up/down to move; left/right to change a value |
| 🔫 **Trigger** (either hand) | select the option |
| **B / Y** | go back |

### Your body

| | |
|---|---|
| **Turn your head** | turns the camera. Max's body follows with a delay, so it doesn't make you sick |
| **Take a real step** | Max walks that way |
| **Crouch / lean** | your eye actually moves (6 degrees of freedom) |

### Keyboard keys (optional fine-tuning)

| key | what it does |
|---|---|
| **M** / **N** | raise / lower eye height, one centimetre per press |
| **,** / **.** | move the eyes closer / further apart, one millimetre per press |

**Every button can be remapped** in `MaxPayne2VR.ini`, and most of them **while the game is
running**.

---

## Settings

Everything lives in `MaxPayne2VR.ini`, documented **setting by setting** — what it does, what
values it takes, and what you will notice when you change it.

Most of them apply **without closing the game**: save the file and the mod picks it up. The ones
that can't say so.

> The `.ini` is written in Spanish. Every setting name is in Spanish too, so the file and the
> game match. If you need it in English, open an issue and it can be translated.

---

## Troubleshooting

| what you see | what to check |
|---|---|
| The game starts but **never enters the headset** | is Virtual Desktop connected **before** you launch the game? Are you using SteamVR? It cannot work (see above) |
| It looks **blurry** | the launcher resolution. Set it to the maximum (step 4) |
| It looks **flat**, no depth | DXVK is missing: check that `d3d8.dll` and `d3d9.dll` are in the game folder |
| **Nothing** changes when you launch | `winmm.dll` is in the wrong folder. It must sit **next to `MaxPayne2.exe`**, not inside `mod\` |
| The arm behaves strangely | stand in a T-pose for a few seconds so it measures you again |

The mod writes a **log** in the game folder saying **what was requested and what was actually
applied**. If you open an issue, attach it: it answers half the questions on its own.

---

## Uninstalling

Delete `winmm.dll`. The game goes back to the original.
**No game file has been modified at any point.**

---

## Credits and licences

Mod created by **betotron** — [github.com/betotron](https://github.com/betotron)
Powered by **[techbuzzo.com](https://techbuzzo.com)**

*Max Payne 2: The Fall of Max Payne* is the property of **Remedy Entertainment** and **Rockstar
Games**. This mod **contains and distributes no game files**: it is two files of its own that sit
next to the game. You need to own the original game.

`winmm.dll` includes the **OpenXR** loader (The Khronos Group) under the Apache 2.0 licence.
The full text is in [`LICENCIAS.txt`](LICENCIAS.txt).

---

## Version

| | |
|---|---|
| build | `C-235` |
| SHA-256 of `winmm.dll` | `76FD1F14D4E9AE3B78565A52AA1B020D3705998C1BCF5DC818430C11642F8F2E` |

