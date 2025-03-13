zephyr_library()

zephyr_library_sources_ifdef(CONFIG_PMW3610 src/pmw3610.c)


zephyr_include_directories(${APPLICATION_SOURCE_DIR}/include)

target_sources(app PRIVSTE ${APPLICATION_SOURCE_DIR}/src/zmk_keymap.c)
message(STATUS "APPLICATION_SOURCE_DIR: ${APPLICATION_SOURCE_DIR}")