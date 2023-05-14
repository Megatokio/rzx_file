cmake_minimum_required(VERSION 3.5)

project(rzx_file LANGUAGES C)

find_package(ZLIB REQUIRED)

add_executable(rzx_file rzx.c rzx.h test.c)
target_link_libraries(rzx_file ZLIB::ZLIB)

file(COPY ${CMAKE_CURRENT_SOURCE_DIR}/test.z80
    DESTINATION ${CMAKE_CURRENT_BINARY_DIR})

install(TARGETS rzx_file
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)
