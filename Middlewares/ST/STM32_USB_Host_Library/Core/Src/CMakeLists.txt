set(sources
    usbh_core.c
    usbh_ctlreq.c
    usbh_ioreq.c
    usbh_pipes.c
)

target_sources(STM32_USB_Host_Library PUBLIC ${sources})