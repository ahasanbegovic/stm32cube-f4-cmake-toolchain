set(sources
    main.c
    stm32f4xx_it.c
    system_stm32f4xx.c
    ts_calibration.c
    usbh_conf.c
    usbh_diskio_dma.c
)

target_sources(${elf_file} PUBLIC ${sources})