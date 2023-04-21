
# # FMC/FSMC only defined for some F4 families
# if (DEVICE_FAMILY STREQUAL STM32F427_437xx OR DEVICE_FAMILY STREQUAL STM32F429xx OR DEVICE_FAMILY STREQUAL STM32F439xx OR DEVICE_FAMILY STREQUAL STM32F446xx OR DEVICE_FAMILY STREQUAL STM32F469_479xx)
#   set(sources ${sources} Src/stm32f4xx_hal_fmc.c)
# else()
#   set(sources ${sources} Src/stm32f4xx_hal_fsmc.c)
# endif()

add_library(stm32f4-toolchain)

#target_link_libraries(stm32f4-toolchain PUBLIC FatFs)
#target_link_libraries(stm32f4-toolchain PUBLIC STM32_USB_Host_Library)

# set up some defines for the StdPeriph library
target_compile_definitions(stm32f4-toolchain PUBLIC USE_STDPERIPH_DRIVER)
target_compile_definitions(stm32f4-toolchain PUBLIC ${DEVICE_FAMILY})
target_compile_definitions(stm32f4-toolchain PUBLIC HSE_VALUE=${HSE_VALUE})

# additional compiler options: use size-optimized version of library in release build, use -O0 in debug build
if(CMAKE_BUILD_TYPE MATCHES Debug)
  set(additional_flags -O0)
else()
  set(additional_flags -Os)
endif()

target_compile_options(stm32f4-toolchain PRIVATE ${additional_flags})

add_subdirectory(Drivers)
add_subdirectory(Middlewares)
#add_subdirectory(Projects)