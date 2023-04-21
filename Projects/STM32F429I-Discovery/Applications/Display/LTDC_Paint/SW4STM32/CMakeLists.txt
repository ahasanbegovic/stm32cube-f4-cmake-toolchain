set(sources
    startup_stm32f429xx.s
)

target_sources(${elf_file} PUBLIC ${sources})

add_subdirectory(STM32F429I-Discovery)