# __Example: *st25dv64kc_protection_i2c*__

How to use ST25DV64KC part API.

It illustrates it by configuring EEPROM user zones and applying different I2C read/write protection levels, then validating access with closed and open security sessions.


## __1. Detailed scenario__

__Initialization phase__: At main program start, the `mx_system_init()` function is called. It initializes the peripherals, nonvolatile memory (such as flash memory, NVM, or external memories), MPU regions (if applicable), the system clock, and the SysTick.

The application executes the following __example steps__:

__Step 1__: Initializes ST25DV64KC communication and computes EEPROM geometry

__Step 2__: Creates 4 user zones and applies per-zone protection policies

__Step 3__: Verifies read/write behavior first with closed session, then with valid I2C password session

__End of example__: It is an endless example where the protection demonstration runs during initialization and main loop remains idle

You can follow these execution steps in the terminal logs:

```text
[INFO] Step 1: ST25DV64KC init completed
[INFO] Step 2: User zones configured with protections
[INFO] Step 3: Access checks completed with/without password
```


## __2. Example configuration__

This example demonstrates the following components:

- Part st25dvxxkc.c/.h
- User zone mapping APIs
- I2C protection and security session/password APIs
- Basic stdio traces

In this example, the ST25DV64KC component is configured through I2C IO operations.
Once I2C and board-specific tag settings are initialized, EEPROM zones are partitioned and protected to demonstrate secure access control.


## __3. Hardware environment and setup__

### __3.1. Generic Setup__

This section describes the hardware setup principles that apply to any board.

### __3.2. Specific board setups__

<details>
<summary>On STM32C5 series.</summary>
  <summary>On board NUCLEO-C562RE with NFC07A1 expansion board.</summary>

  Ensure the NFC07A1 expansion board is mounted correctly on the NUCLEO-C562RE board,
and that I2C wiring and power are provided by the Arduino connector.

</details>

## __4. Software setup__

To create a functional project, complete the following steps:
- Select the appropriate IoC2 file based on the combination of NUCLEO and NFC expansion boards. For example, use c562re_nfc07a1_st25dv64kc_protection_i2c.ioc2.
- Open the IoC2 file with STM32CubeMX2.
- Select the preferred toolchain and generate the source code.
- Copy the example.c, example.h, main.c, and main.h files into the project folder of the generated code.
- Open the Integrated Development Environment (IDE), add all copied .c and .h files to the project.
- Add the USE_TRACE=1 to the global variables of the project.
- Compile the project.

## __5. Troubleshooting__

No specific debug tips.


## __6. See Also__

More information about ST25DV64KC part driver can be found in the [ST25DV64KC documentation](https://www.st.com/en/nfc/st25dv64kc.html)

More information about the STM32 ecosystem can be found in the [STM32 MCU Developer Zone](https://www.st.com/content/st_com/en/stm32-mcu-developer-zone.html).


## __7. License__

Copyright (c) 2026 STMicroelectronics.

This software is licensed under terms that can be found in the LICENSE file in the root directory
of this software component.
If no LICENSE file comes with this software, it is provided AS-IS.
