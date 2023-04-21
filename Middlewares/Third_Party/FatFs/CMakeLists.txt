add_library(FatFs)

set_target_properties(FatFs PROPERTIES
    EXCLUDE_FROM_ALL TRUE
)

add_subdirectory(src)