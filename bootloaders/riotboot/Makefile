# Default RIOT bootloader
APPLICATION = riotboot

# Default testing board
BOARD ?= samr21-xpro

# Select the boards with riotboot feature
FEATURES_REQUIRED += riotboot

# Set RIOTBOOT_BUILD to indicate a riotboot application build
RIOTBOOT_BUILD = 1
# Provide a define to detect if building the bootloader
CFLAGS += -DRIOTBOOT

# Disable unused modules
CFLAGS += -DNDEBUG -DLOG_LEVEL=LOG_NONE
DISABLE_MODULE += core_init core_msg core_panic
DISABLE_MODULE += auto_init

# avoid using stdio
USEMODULE += stdio_null

# Include riotboot flash partition functionality
USEMODULE += riotboot_slot

# RIOT codebase
RIOTBASE ?= $(CURDIR)/../../

include $(RIOTBASE)/Makefile.include

# limit riotboot bootloader size
# TODO: Manage to set this variable for boards which already embed a
# bootloader, currently it will be overwritten
ROM_LEN := $(RIOTBOOT_LEN)
