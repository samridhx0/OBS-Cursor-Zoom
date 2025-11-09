# OBS-Lua-Zoom-Fix

**✓ Updated and Fixed for OBS Studio 30.x**

A fixed and updated version of the OBS Zoom to Mouse script, compatible with OBS Studio 30.x and later.

![GITHUB](https://github.com/user-attachments/assets/b3983af6-31ea-4bfe-a050-abc6cafacc7f)


> This script is designed for OBS Studio 30.x and later. It uses the new scene item API and will not work with OBS 29.x or earlier.

> **Quick Start**: [Download obs-zoom-to-mouse.lua](obs-zoom-to-mouse.lua) → OBS → Tools → Scripts → + → Done!


## About

**This is an updated and fixed version of the excellent [obs-zoom-to-mouse](https://github.com/BlankSourceCode/obs-zoom-to-mouse) script by BlankSourceCode. The original script provides zoom functionality for OBS Studio display-capture sources, allowing you to zoom into your screen and follow your mouse cursor.**

This repository contains fixes for compatibility with the latest OBS Studio versions.

## Original Features

An OBS lua script to zoom a display-capture source to focus on the mouse. 

- Works on **Windows**, **Linux**, and **Mac**
- Smooth zoom animations
- Auto-follow mouse tracking with customizable behavior
- Support for multiple monitors
- Remote mouse tracking support (dual machine setups)

## Install

1. Download or clone this repository
2. Get the `obs-zoom-to-mouse.lua` file
3. Launch OBS Studio
4. In OBS, add a `Display Capture` source (if you don't have one already)
5. In OBS, open **Tools** → **Scripts**
6. In the Scripts window, press the **+** button to add a new script
7. Find and add the `obs-zoom-to-mouse.lua` script

### Recommended Display Capture Settings

For best results, use the following settings on your `Display Capture` source:

* **Transform:**
  * Positional Alignment - `Top Left`
  * Bounding Box type - `Scale to inner bounds`
  * Alignment in Bounding Box - `Top Left`
  * Crop - All **zeros**

* **For cropping**, add a Filter → `Crop/Pad`:
  * Relative - `False`
  * X - Amount to crop from left side
  * Y - Amount to crop from top side
  * Width - Full width of display minus X + amount to crop from right side
  * Height - Full height of display minus Y + amount to crop from bottom side

**Note:** If you don't use this setup, the script will attempt to **automatically convert your settings** to zoom-compatible ones. This may have undesired effects on your layout.

## Usage

### Basic Configuration

Customize these settings in the OBS Scripts window:

* **Zoom Source**: The display capture in the current scene to use for zooming
* **Zoom Factor**: How much to zoom in (1-5x)
* **Zoom Speed**: Speed of the zoom in/out animation (0.01-1.0)
* **Auto follow mouse**: Automatically track the cursor while zoomed in
* **Follow outside bounds**: Track cursor even when outside source bounds
* **Follow Speed**: Speed at which the view follows the mouse
* **Follow Border**: Distance from edge (%) that re-enables mouse tracking
* **Lock Sensitivity**: How close tracking needs to get before locking position
* **Auto Lock on reverse direction**: Stop tracking if mouse reverses direction

### Hotkeys

In OBS, open **File** → **Settings** → **Hotkeys**:

* Add a hotkey for `Toggle zoom to mouse` to zoom in and out
* Add a hotkey for `Toggle follow mouse during zoom` (optional) to control tracking

### Advanced Settings

* **Show all sources**: Allow selecting any source (requires manual position setup)
* **Set manual source position**: Override auto-calculated position/size values
* **Remote mouse listener**: Enable UDP socket server for dual-machine setups

## Platform-Specific Notes

### Windows
- Should work out of the box with Display Capture sources

### Linux
- May need to install the [loopback package](https://obsproject.com/forum/threads/obs-no-display-screen-capture-option.156314/) for XSHM display capture
- Works with Pipewire sources (requires manual position setup)

### Mac
- Supports both legacy `display_capture` and newer `screen_capture` sources
- May need to set Monitor Height when using manual source position

## What's Fixed

This version includes fixes for:
- Compatibility with OBS Studio 30.x and later
- Updated API calls for recent OBS versions
- Platform detection improvements
- Better error handling

## Credits

Original script created by [BlankSourceCode](https://github.com/BlankSourceCode)

Original repository: https://github.com/BlankSourceCode/obs-zoom-to-mouse

Fixed for latest version by me (@samridhx0)

## License

This project maintains the same license as the original work.

