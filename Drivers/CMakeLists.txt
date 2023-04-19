add_subdirectory(STM32F4xx_HAL_DRIVER)
#add_subdirectory(CMSIS)


target_include_directories(stm32f4-toolchain PUBLIC CMSIS/Core/Include)
target_include_directories(stm32f4-toolchain PUBLIC CMSIS/Device/ST/STM32F4xx/Include)