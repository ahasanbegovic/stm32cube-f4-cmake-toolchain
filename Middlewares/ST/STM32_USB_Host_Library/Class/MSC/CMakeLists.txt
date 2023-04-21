set(sources
    Src/usbh_msc_bot.c
    Src/usbh_msc_scsi.c
    Src/usbh_msc.c
)

target_sources(STM32_USB_Host_Library PUBLIC ${sources})

target_include_directories(STM32_USB_Host_Library PUBLIC Inc)