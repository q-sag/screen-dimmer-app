# Screen Dimmer: user guide

Screen Dimmer darkens your screens below what the monitor's own brightness buttons can reach. Use one
slider for every screen, or give each screen its own level.

![The Screen Dimmer window in All screens mode](images/window-all-screens.png)

## Contents

1. [Install](#install)
2. [First launch](#first-launch)
3. [All screens mode](#all-screens-mode)
4. [Per screen mode](#per-screen-mode)
5. [Shortcuts, including the mouse wheel](#shortcuts-including-the-mouse-wheel)
6. [Tray icon](#tray-icon)
7. [Start with Windows](#start-with-windows)
8. [Examples](#examples)
9. [Settings file](#settings-file)
10. [Limits and troubleshooting](#limits-and-troubleshooting)

## Install

Get Screen Dimmer from the **Microsoft Store**: search for "Screen Dimmer" and select **Get** (it is a
small one-time purchase). Store installs update themselves and uninstall cleanly.

Requires Windows 10 version 1809 or later, 64-bit.

## First launch

The window opens once, and Screen Dimmer starts living in the notification area (the tray, next to the
clock). It is set to start with Windows. After that it starts quietly in the tray, and you open the
window by clicking its icon. You may need to drag the icon out of the "hidden icons" arrow to keep it
visible.

Closing the window with the **X** does not quit the app. It keeps running in the tray, so the shortcuts
keep working. To quit, right-click the tray icon and choose **Exit**.

## All screens mode

This is the default. One slider dims every connected screen by the same amount.

- **0%** means no dimming.
- **100%** is about 97% black. The screen is never switched fully off, so you can still find your way
  back.
- Drag the slider, click anywhere on it, scroll the mouse wheel over it (steps of 5), or focus it and use
  the arrow keys (Shift for steps of 10).

Under the percentage, the app shows how many screens it found.

## Per screen mode

Select **Per screen** at the top of the window.

![Per screen mode, with three different levels](images/window-per-screen.png)

- Every connected screen gets a row with its own slider, named **Screen 1**, **Screen 2** and so on,
  numbered **left to right** by position on your desktop. Each row also shows the screen's resolution and
  whether it is the primary screen.
- Not sure which row is which monitor? Select **Identify**. A big number appears in the middle of every
  screen for about two seconds.
- Each screen's level is remembered by the monitor itself, not by its number. If you unplug a screen and
  plug it back in, it comes back at the level you set. A screen the app has never seen starts at the
  current All screens level.
- All screens and Per screen keep separate settings, so you can switch between them without losing either.
- Plugging screens in or out while the app runs is picked up within a couple of seconds.

## Shortcuts, including the mouse wheel

Defaults:

| Action | Mouse wheel | Keyboard |
|---|---|---|
| Reduce dim | Ctrl+Alt+Scroll ↑ | Ctrl+Alt+Up |
| Add dim | Ctrl+Alt+Scroll ↓ | Ctrl+Alt+Down |
| Remove dimming | (none) | Ctrl+Alt+0 |

Each press or notch changes the level by 5%.

**Which screen do they affect?** In All screens mode, all of them. In Per screen mode, **the screen the
mouse pointer is on**. Point at the screen you want to change, hold Ctrl+Alt and scroll. This is the
quickest way to change one screen without opening the window.

**Changing a shortcut**

1. Select the shortcut button in the window. It reads "Press shortcut…".
2. Press the new keys, or hold a modifier and scroll the wheel up or down.
3. The new shortcut is saved immediately.

Notes:

- A shortcut needs at least one modifier (Ctrl, Alt, Shift or Win), so it can never get in the way of normal
  typing or scrolling.
- Press **Esc** to cancel. **Right-click** a button to clear it.
- Each action has two slots, for example one wheel shortcut and one keyboard shortcut.
- If you assign a shortcut that is already used by another action here, it moves to the new action.
- While a shortcut matches, Screen Dimmer handles it and the app underneath does not see it. If another app
  already uses the same chord, choose a different one.

## Tray icon

- **Left-click**: show or hide the window.
- **Right-click** menu:
  - **Open Screen Dimmer**
  - **Presets**: No dimming, 25%, 50%, 75%, 90%. They apply to the current mode: the single level in All
    screens mode, or every screen in Per screen mode.
  - **Dim each screen separately**: switches between the two modes.
  - **Start with Windows**
  - **Exit**
- Hover over the icon to see the current levels, for example `100% / 20% / 0%`.

## Start with Windows

Turn it on or off with the switch in the window, or in the tray menu. It is on by default.

If Windows reports that start-up is blocked, open **Settings → Apps → Startup** and turn Screen Dimmer
on there. Windows lets you override apps' start-up choices in that list.

## Examples

**A quiet room at night.** Someone is asleep in the room, but you still need a screen. Set the level to
50–75%. Video flashes stop lighting up the room, and the screen is still readable.

**Video on one screen, work on another.** Switch to Per screen. Dim the screen with the video heavily,
and leave the screen you work on at a low level in a dark theme. You can change either from the keyboard
by pointing at the screen and scrolling with Ctrl+Alt.

**Presentations and recordings.** Use **Remove dimming** (Ctrl+Alt+0) on the screen you are sharing.

![The same picture at 25%, 50% and 100% dim](images/use-case-dim-levels.png)

*The same picture at 25%, 50% and 100% dim. The dimming is a black layer over the screen, so what you
see here matches what the app does.*

## Settings file

Levels, mode and shortcuts are saved automatically in `settings.json` in the app's data folder
(`%APPDATA%\ScreenDimmer` for the unpackaged version; the Store version keeps it in its own package data
folder). You rarely need to edit it. One useful value:

- `Step`: how much each shortcut press changes the level (default 5, range 1 to 50). Quit the app
  before editing the file.

To reset everything, quit the app and delete the file.

## Limits and troubleshooting

**It does not change the backlight.** Screen Dimmer puts a black layer over the picture. The panel
still draws the same power and light output behind it. For the best result, also lower the monitor's
own brightness, then use Screen Dimmer for the rest.

**Screenshots and screen recordings.** They capture what is on the screen, including the dimming.

**Full-screen games and some video players.** Programs in exclusive full-screen mode can draw above the
dimming layer. Borderless-window mode usually works.

**Shortcuts do nothing.**
- Check that the app is running (tray icon).
- Another program may use the same chord. Assign a different one.
- Windows may not pass keyboard and mouse input to a normal program while a window running as
  administrator has focus. Switch to a normal window, or use the window or tray menu.

**The wrong screen changes in Per screen mode.** Shortcuts act on the screen under the mouse pointer,
not on the screen with the active window.

**The window is on a screen I can't see.** Click the tray icon twice (hide, then show), or start the app
again from the Start menu. It brings the window forward.

**I turned the dimming to 100% and can't see anything.** Press Ctrl+Alt+0, or point at the screen and
scroll with Ctrl+Alt. Or right-click the tray icon (it is still faintly visible) and choose
**No dimming**.

**Uninstall.** Remove it in **Settings → Apps → Installed apps**.
