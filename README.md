# RP2020 Pico Bootstrap

This repository contains my Raspberry Pico project bootstrap files.

It provides a VS Code/Platform IO integration with one-click compilation&uploading.

It also provides a VS Code integrated one-click Openocd/GDB debugging session, for which you only need one Raspberry Pico board.

![](examples/vs_code_debugging_session.png)

## Prerequisites

To work with this repository, you need to have the following projects up and running:

- [WizIO Pico](https://github.com/Wiz-IO/wizio-pico/)
- [Pico Debug](https://github.com/majbthrd/pico-debug)

## Setup for Compilation/Upload

For this to work, you need to set two environment variables:

- PICO_USB_DIR - directory path where your Raspberry Pico is mounted in USB storage/bootsel mode
- PICO_SERIAL_DIR - directory path where your Raspberry Pico is mounted in serial-over-USB mode

See the file `plattform.io` for more configuration options.

If all is done, you can compile and upload your Pico program with the default PlatformIO steps or by using the icons in your VS code bottom toolbar.

## Setup for Debugging

First, set these environment variables:

- PICO_OPENOCD_PATH - directory where you downloaded and compiled OpenOCD
- PICO_DEBUG_SDK_PATH_PATH - directory to the [Pico Debug SDK branch], get it with `git clone https://github.com/majbthrd/pico-sdk.git --branch pll_init`

See `.vscode/launch.json` for more configuration options.

Second, grab the latest [pico debug UF2 file](https://github.com/majbthrd/pico-debug/releases/tag/v10.03) and upload it to your Raspberry Pico.

Third, start the debug compilation by `Terminal -> Run Task -> Debug Build`. When completed, start the debugging session with `Run -> Start Debugging`.
