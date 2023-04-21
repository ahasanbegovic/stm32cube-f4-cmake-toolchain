set(sources
    stm32f4xx_hal.c
    stm32f4xx_hal_cortex.c
    stm32f4xx_hal_gpio.c
    stm32f4xx_hal_rcc.c
    stm32f4xx_hal_rcc_ex.c
    stm32f4xx_hal_hcd.c
    stm32f4xx_hal_ltdc.c
    stm32f4xx_ll_fmc.c
    stm32f4xx_ll_usb.c
    stm32f4xx_hal_pcd.c
    stm32f4xx_hal_sdram.c
    stm32f4xx_hal_spi.c
    stm32f4xx_hal_dma2d.c
    stm32f4xx_hal_dma.c
    stm32f4xx_hal_dma_ex.c
    stm32f4xx_hal_i2c.c
    stm32f4xx_hal_pwr_ex.c
)

target_sources(stm32f4-toolchain PUBLIC ${sources})