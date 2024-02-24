# Project Setup Instructions

This README provides detailed instructions on how to set up the project environment. Please follow these steps carefully.

## Steps to Get Started

1. **Example Step One: Create a Python Virtual Environment**  
   Run the following command to create a virtual environment named `zephyr_py_venv`:  
   ```bash
   python3 -m venv zephyr_py_venv
   ```

2. **Activate the Virtual Environment**  
   Activate the created virtual environment:  
   ```bash
   source zephyr_py_venv/bin/activate
   ```

3. **Step 3**  
   Use pip to install `west`:  
   ```bash
   pip install west
   ```

4. **Etc**  
   Run the following commands to initialise the `zephyrproject`:  
   ```bash
   west init zephyrproject
   cd zephyrproject
   west update
   ```

# Building and Flashing

From here on building and flashing is done from the app subdirectory of zmk

    ```bash
    cd app
    ```

## Building

### Pristine Building

When building for a new board and/or shield after having built one previously, you may need to enable the pristine build option. This option removes all existing files in the build directory before regenerating them, and can be enabled by adding either --pristine or -p to the command:

    ```bash
    west build -p -b nice_nano_v2 -- -DSHIELD=bond
    ```

### Keyboard with Onboard MCU

Keyboards with onboard MCU chips are simply treated as the board as far as Zephyr™ is concerned.

Given the following:

Keyboard: Planck (rev6)
Keymap: default
you can build ZMK with the following:

    ```bash
    west build -b planck_rev6
    ```

### External Modules

ZMK supports loading additional boards, shields, code, etc. from external Zephyr modules, facilitating out-of-tree management and versioning independent of the ZMK repository. To build with any additional modules, use the ZMK_EXTRA_MODULES define added to your west build command.

For instance, building with the my-vendor-keebs-module checked out to your documents directory, you would build like:

```bash
west build -b nice_nano_v2 -- -DSHIELD=vendor_shield -DZMK_EXTRA_MODULES="C:/Users/myUser/Documents/my-vendor-keebs-module"
```


When adding multiple modules, make sure they are separated by a semicolon, e.g.:

```bash
west build -b nice_nano_v2 -- -DSHIELD=vendor_shield -DZMK_EXTRA_MODULES="C:/Users/myUser/Documents/my-vendor-keebs-module;C:/Users/myUser/Documents/my-other-keebs-module"
```

## Flashing

The above build commands generate a UF2 file in build/zephyr (or build/left|right/zephyr if you followed the instructions for splits) and is by default named zmk.uf2. If your board supports USB Flashing Format (UF2), copy that file onto the root of the USB mass storage device for your board. The controller should flash your built firmware, unmount the USB storage device and automatically restart once flashing is complete.

Alternatively, if your board supports flashing and you're not developing from within a Dockerized environment, enable Device Firmware Upgrade (DFU) mode on your board and run the following command to flash:

```bash
west flash
```