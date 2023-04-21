set(sources
    stm32f429i_discovery.c
    stm32f429i_discovery_eeprom.c
    stm32f429i_discovery_gyroscope.c
    stm32f429i_discovery_io.c
    stm32f429i_discovery_lcd.c
    stm32f429i_discovery_sdram.c
    stm32f429i_discovery_ts.c
)

target_sources(stm32f4-toolchain PUBLIC ${sources})

target_include_directories(stm32f4-toolchain PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})