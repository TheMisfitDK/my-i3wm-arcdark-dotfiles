# my-i3wm-arcdark-dotfiles
My custom Arc-Dark i3 window manager dotfiles for Arch/EndeavourOS. Focused on clean aesthetics, and custom panel scripts.

# About this Project
> A clean, modernized i3wm setup for EndeavourOS featuring an Arc-Dark aesthetic, blue accents, interactive i3blocks, and a custom Rofi USB manager.

<p align="center">
  <!-- Replace the URL below with the actual path to your screenshot once uploaded -->
  <img src="https://github.com/user-attachments/assets/b145d03a-3602-4843-b92d-a19041b867d7" />
</p>

## About This Setup

This repository contains my customized i3 window manager configuration, i3blocks panel setup, and custom bash scripts. Originally based on the default EndeavourOS i3 setup, these dotfiles have been slightly overhauled to provide a clean, modern, and interactive desktop experience while retaining standard default EndeavourOS keybindings.

## The Aesthetic: Arc-Dark & Blueish Accents

The visual language of this setup relies on high-contrast, cool-toned colors. The goal was to replace harsh, absolute blacks with deep, easy-on-the-eyes greys, highlighted by vibrant blues for active elements.

| Element | Color Hex | Usage |
| :--- | :--- | :--- |
| **Background Base** | `#2f343f` | The classic Arc Dark grey used for the panel background and inactive windows. |
| **Primary Accent** | `#89b4fa` | A bright, clear blue used for focused window borders, panel separators, and active icons. |
| **Primary Text** | `#cdd6f4` | A soft, cool white for highly legible text across the system. |
| **Urgent / Alerts** | `#f38ba8` | A contrasting red for urgent workspaces and critical system warnings. |

## Key Configuration Changes

*   **Clean Typography:** Configured with `Inter` for a modern, minimalist interface.
*   **Window Management:** Implements inner gaps of `6` and outer gaps of `3` for a spacious floating look, with 1px borders to keep the screen uncluttered.
*   **Smart Workspace Rules:** Window class assignments use case-insensitive regex (e.g., `(?i)librewolf`) to ensure applications always map to their correct workspaces regardless of how the system capitalizes them.
*   **Custom Panel Separators:** The default i3blocks separators are disabled globally. Instead, custom pipe (`|`) text blocks colored in the primary accent blue are used strictly between categorical sections (System, Network, Audio).

## Interactive Scripts & Modules

*   **USB Device Manager:** A custom bash script (`usb-manager`) that sits on the panel. It automatically detects plugged-in USB drives and uses `rofi -dmenu` to provide a clickable GUI for mounting, unmounting, and safely powering off drives via `udisksctl`.
*   **Clickable Audio Control:** The volume module in i3blocks includes built-in mouse detection to instantly launch `pavucontrol` (volume mixer) upon a left-click.

## Keybindings

All keybindings remain identical to the default **EndeavourOS i3wm** configuration:
*   `$mod4` is mapped to the **Super / Windows key**.
*   `$mod4 + Return`: Open terminal (`xfce4-terminal`).
*   `$mod4 + d`: Open application launcher (`rofi`).
*   `$mod4 + q`: Kill focused window.
*   `$mod4 + Print / $mod4 + lshift + print`: Take screenshots with `screengrab`.
*   `$mod4 + Shift + r`: Restart i3 in place.
*   `$mod + Shift + e`: Open power/exit menu.

## Required Dependencies

To get everything working exactly as shown in these dotfiles, ensure the following packages are installed on your Arch/EndeavourOS system:

*   **Font:** `ttf-inter`
*   **Menu & Launchers:** `rofi` (required for both the application launcher and the USB manager script).
*   **Drive Management:** `udisks2` (handles the backend mounting logic without requiring root/sudo).
*   **Media Keys:** `playerctl` (for keyboard media controls).
*   **Screenshots:** `screengrab` (used by the default EndeavourOS screenshot keybindings).
