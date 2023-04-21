add_library(STM32_USB_Host_Library)

set_target_properties(STM32_USB_Host_Library PROPERTIES
    EXCLUDE_FROM_ALL TRUE
)

target_link_libraries(STM32_USB_Host_Library PUBLIC stm32f4-toolchain)
#target_link_libraries(STM32_USB_Host_Library PUBLIC RTOS2)

add_subdirectory(Class)
add_subdirectory(Core)