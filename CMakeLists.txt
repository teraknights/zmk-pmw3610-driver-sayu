# ヘッダが入ってるディレクトリを洗い出すマクロ
MACRO(HEADER_DIRECTORIES return_list)
   FILE(GLOB_RECURSE new_list *.h)
   SET(dir_list "")
   FOREACH(file_path ${new_list})
       GET_FILENAME_COMPONENT(dir_path ${file_path} PATH)
       SET(dir_list ${dir_list} ${dir_path})
   ENDFOREACH()
   LIST(REMOVE_DUPLICATES dir_list)
   SET(${return_list} ${dir_list})
ENDMACRO()
# マクロ呼び出し
HEADER_DIRECTORIES(header_dir_list)
# 件数カウント
list(LENGTH header_dir_list header_dir_list_count)
message(STATUS "Count: ${header_dir_list_count}")
# リスト一覧出力
message(STATUS "++++List++++: ${header_dir_list}")

zephyr_library()

zephyr_library_sources_ifdef(CONFIG_PMW3610 src/pmw3610.c)


zephyr_include_directories(${APPLICATION_SOURCE_DIR}/include)

#target_sources(app PRIVSTE ${APPLICATION_SOURCE_DIR}/src/zmk_keymap.c)
message(STATUS "APPLICATION_SOURCE_DIR: ${APPLICATION_SOURCE_DIR}")