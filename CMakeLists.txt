zephyr_library()

zephyr_library_sources_ifdef(CONFIG_PMW3610 src/pmw3610.c)

zephyr_include_directories(${APPLICATION_SOURCE_DIR}/include)

add_library(zmk-pmw3610-driver-sayu STATIC
    src/pmw3610.c
)
target_link_libraries(zmk-pmw3610-driver-sayu PRIVATE zmk)