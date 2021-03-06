# Target file name (without extension).
PROJECT = ch

# Directory common source files exist
TMK_DIR = ../../tmk_keyboard/tmk_core

# Directory keyboard dependent files exist
TARGET_DIR = .

# project specific files
SRC =   matrix.c \
        keymap_common.c \
        led.c \
        user_thread.c

ifdef KEYMAP
    SRC := keymap_$(KEYMAP).c $(SRC)
else
    SRC := keymap_plain.c $(SRC)
endif

CONFIG_H = config.h

## chip/board settings
# the next two should match the directories in
#  <chibios>/os/hal/ports/$(MCU_FAMILY)/$(MCU_SERIES)
MCU_FAMILY = STM32
MCU_SERIES = STM32F0xx
# linker script to use
# it should exist either in <chibios>/os/common/ports/ARMCMx/compilers/GCC/ld/
#  or <this_dir>/ld/
MCU_LDSCRIPT = STM32F042x6
# startup code to use
# is should exist in <chibios>/os/common/ports/ARMCMx/compilers/GCC/mk/
MCU_STARTUP = stm32f0xx
# it should exist either in <chibios>/os/hal/boards/
#  or <this_dir>/boards
BOARD = KB45P
# Cortex version
# Teensy LC is cortex-m0; Teensy 3.x are cortex-m4
MCU  = cortex-m0
# ARM version, CORTEX-M0/M1 are 6, CORTEX-M3/M4/M7 are 7
ARMV = 6
# If you want to be able to jump to bootloader from firmware on STM32 MCUs,
# set the correct STM32_BOOTLOADER_ADDRESS. Either set it here, or define it in
# ./bootloader_defs.h or in ./boards/<FOO>/bootloader_defs.h (if you have
# a custom board definition that you plan to reuse).
# If you're not setting it here, leave it commented out.
# It is chip dependent, the correct number can be looked up here (page 175):
# http://www.st.com/web/en/resource/technical/document/application_note/CD00167594.pdf
# This also requires a patch to chibios
#   <tmk_dir>/tmk_core/tool/chibios/ch-bootloader-jump.patch
# or a custom board file.
#STM32_BOOTLOADER_ADDRESS = "0x1FFFC800"

# Build Options
#   comment out to disable the options.
#
#BOOTMAGIC_ENABLE = yes # Virtual DIP switch configuration
## BOOTMAGIC is not supported on STM32 chips yet.
MOUSEKEY_ENABLE = yes   # Mouse keys
EXTRAKEY_ENABLE = yes   # Audio control and System control
CONSOLE_ENABLE = yes    # Console for debug
COMMAND_ENABLE = yes    # Commands for debug and configuration
SLEEP_LED_ENABLE = yes  # Breathing sleep LED during USB suspend
NKRO_ENABLE = yes       # USB Nkey Rollover

include $(TMK_DIR)/tool/chibios/common.mk
include $(TMK_DIR)/tool/chibios/chibios.mk
