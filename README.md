# 🛠️ Build and Installation Guide (Arch Linux Focus)
This guide details how to compile your custom libinput source code and install it onto your system, replacing the official version. You can also download the compiled binary directly *(see /libinput.so.10.13.0)*

## Prerequisites
Ensure you have the necessary tools for cloning and compiling:

*sudo pacman -S base-devel git meson*

## 1. Building and Compiling the Project
Navigate to your repository directory and use meson to compile the modified source code. To build and compile:

*meson setup builddir* 

*meson compile -C builddir*

## 2. Install to the System
This step overwrites the official libinput library with your custom version. The compiled binary is located at your builddir.

*sudo cp -v [Path/To/Your/Binary/libinput.so.10.x.x] /usr/lib/libinput.so.10.x.x*

## 3. Finalize and Test
You must restart your session or system for the changes to take effect, as the Wayland compositor loads libinput on startup.

- By default, palm detection is disabled, but you can enable it by setting LIBINPUT_DISABLE_PALM_DETECTION=0 in your env.
- To change scrolling speed, put LIBINPUT_SCROLL_FACTOR in your env (standard value = 1).


