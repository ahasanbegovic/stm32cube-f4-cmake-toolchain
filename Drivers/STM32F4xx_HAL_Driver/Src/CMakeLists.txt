set(sources
    stm32f4xx_hal.c
    stm32f4xx_hal_cortex.c
    stm32f4xx_hal_gpio.c
    stm32f4xx_hal_rcc.c
    stm32f4xx_hal_rcc_ex.c
)

target_sources(stm32f4-toolchain PUBLIC ${sources})