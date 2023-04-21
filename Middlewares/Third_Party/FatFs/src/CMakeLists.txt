set(sources
    diskio.c
    ff.c
    ff_gen_drv.c
)

target_sources(FatFs PUBLIC ${sources})

target_include_directories(FatFs PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
