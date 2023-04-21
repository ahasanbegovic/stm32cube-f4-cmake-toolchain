#add_subdirectory(EWARM)
#add_subdirectory(MDK-ARM)
add_subdirectory(Src)
add_subdirectory(SW4STM32)

target_include_directories(stm32f4-toolchain PUBLIC Inc)