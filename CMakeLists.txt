zephyr_library()

zephyr_include_directories(${ZEPHYR_BASE}/include)

zephyr_library_sources_ifdef(CONFIG_PMW3610 src/pmw3610.c)

zephyr_include_directories(${APPLICATION_SOURCE_DIR}/include)



zephyr_include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

target_link_libraries(${ZEPHYR_CURRENT_LIBRARY} PRIVATE zmk_keymap)

zephyr_include_directories(${ZMK_BASE}/include)

target_sources(${ZEPHYR_CURRENT_LIBRARY} PRIVATE src/pmw3610.c)

target_link_libraries(${ZEPHYR_CURRENT_LIBRARY} PRIVATE zmk)

