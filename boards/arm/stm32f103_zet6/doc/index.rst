.. _stm32f103_zet6_board:

STM32F103ZET6
################

Overview
********

The STM32F103_ZET6 is ISO STM32

Hardware
********
STM32F103 ZET6 provides the following hardware components:
- TODO
More information about STM32F103RC can be found here:

- `STM32F103 reference manual`_
- `STM32F103 data sheet`_

Supported Features
==================

The Zephyr stm32f103_zet6 board configuration supports the following hardware features:

Other hardware features are not yet supported in this Zephyr port.

The default configuration can be found in the defconfig file:
``boards/arm/stm32f103_zet6/stm32f103_zet6_defconfig``

Connections and IOs
===================

Each of the GPIO pins can be configured by software as output (push-pull or open-drain), as
input (with or without pull-up or pull-down), or as peripheral alternate function. Most of the
GPIO pins are shared with digital or analog alternate functions. All GPIOs are high current
capable except for analog inputs.

Board connectors:
-----------------
.. image:: img/stm32f103_zet6_pin.jpg
   :width: 800px
   :align: center
   :height: 619px
   :alt: Nucleo F103RB connectors

Default Zephyr Peripheral Mapping:
----------------------------------

- UART_1 TX/RX: PA9/PA10
- UART_2 TX/RX: PA2/PA3 (ST-Link Virtual COM Port)
- SPI1 NSS/SCK/MISO/MOSI: PA4/PA5/PA6/PA7
- SPI2 NSS/SCK/MISO/MOSI: PB12/PB13/PB14/PB15
- I2C1 SDA/SCL: PB9/PB8
- PWM1_CH1: PA8
- USER_PB: PC13
- LD1: PA5
- USB_DC DM/DP: PA11/PA12

System Clock
------------

The on-board 8MHz crystal is used to produce a 72MHz system clock with PLL.

Programming and Debugging
*************************

Applications for the ``stm32f103_zet6`` board configuration can be built and
flashed in the usual way (see :ref:`build_an_application` and
:ref:`application_run` for more details).

Flashing
========

There are 2 main entry points for flashing STM32F1X SoCs, one using the ROM
bootloader, and another by using the SWD debug port (which requires additional
hardware such as ST-Link). Flashing using the ROM bootloader requires a special activation
pattern, which can be triggered by using the BOOT0 pin.

Flashing an application to stm32f103 zet6
-----------------------------------------

Here is an example for the :ref:`blinky-sample` application.

.. zephyr-app-commands::
   :zephyr-app: samples/basic/blinky
   :board: stm32f103_zet6
   :goals: build flash

You will see the LED blinking every second.

Debugging
=========

You can debug an application in the usual way.  Here is an example for the
:ref:`blinky-sample` application.

.. zephyr-app-commands::
   :zephyr-app: samples/basic/blinky
   :board: stm32f103_zet6
   :maybe-skip-config:
   :goals: debug

References
**********

.. target-notes::

.. _STM32F103 reference manual:
   http://www.st.com/resource/en/reference_manual/cd00171190.pdf

.. _STM32F103 data sheet:
   http://www.st.com/resource/en/datasheet/stm32f103rc.pdf
