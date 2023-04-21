#add_library(RTOS2)

#set(sources
    #Source/os_systick.c
    #Source/os_tick_gtim.c
    #Source/os_tick_ptim.c
#)

#target_sources(RTOS2 PUBLIC ${sources})

target_include_directories(stm32f4-toolchain PUBLIC Include)
target_include_directories(stm32f4-toolchain PUBLIC Template)
