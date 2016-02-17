PROJECT_NAME = $(shell basename "$(realpath ./)")

APPLICATION_SRCS = $(notdir $(wildcard ./*.c))
APPLICATION_SRCS += nrf_delay.c
APPLICATION_SRCS += softdevice_handler.c
APPLICATION_SRCS += spi_slave.c
APPLICATION_SRCS += ble_advdata.c

LIBRARY_PATHS += ../include

DEVICE = NRF51

ifndef TARGET
	TARGET = Firestorm
endif

TARGET_UPPER = $(shell echo $(TARGET) | tr a-z A-Z)
BOARD = BOARD_$(TARGET_UPPER)

USE_SOFTDEVICE = s110

SDK_VERSION = 9
NRF_BASE_PATH ?= ../../nrf5x-base/
TEMPLATE_PATH ?= ../../nrf5x-base/nrf51-pure-gcc-setup/template/
SOFTDEVICE ?= ../../nrf5x-base/softdevice/s110_nrf51_8.0.0_softdevice.hex
SDK_PATH ?= ../../nrf5x-base/sdk/nrf51_sdk_9.0.0/

LIBRARY_PATHS += .  ../../include
LIBRARY_PATHS += $(NRF_BASE_PATH)/peripherals/
SOURCE_PATHS += ../../src

CFLAGS = -Os
GDB_PORT_NUMBER = 2331

include $(TEMPLATE_PATH)Makefile
