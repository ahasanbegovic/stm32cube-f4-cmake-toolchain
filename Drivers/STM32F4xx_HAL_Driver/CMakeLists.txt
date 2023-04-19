set(sources
    Src/stm32f4xx_hal.c
    Src/stm32f4xx_hal_cortex.c
    Src/stm32f4xx_hal_gpio.c
    Src/stm32f4xx_hal_rcc.c
    Src/stm32f4xx_hal_rcc_ex.c
)

# # FMC/FSMC only defined for some F4 families
# if (DEVICE_FAMILY STREQUAL STM32F427_437xx OR DEVICE_FAMILY STREQUAL STM32F429xx OR DEVICE_FAMILY STREQUAL STM32F439xx OR DEVICE_FAMILY STREQUAL STM32F446xx OR DEVICE_FAMILY STREQUAL STM32F469_479xx)
#   set(sources ${sources} Src/stm32f4xx_hal_fmc.c)
# else()
#   set(sources ${sources} Src/stm32f4xx_hal_fsmc.c)
# endif()

add_library(stm32f4-toolchain ${sources})

# add include directories for StdPeriph library
target_include_directories(stm32f4-toolchain PUBLIC Inc)
target_include_directories(stm32f4-toolchain PUBLIC Inc/Legacy)

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