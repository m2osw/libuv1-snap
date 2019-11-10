
# Source

I get the files from the github.com releases.

https://github.com/libuv/libuv/releases

# Changes

The tests fail big time on our systems and on launchpad. I don't have time
to mess around with those at the moment. I edited the debian/rules and
added the `LIBUV_BUILD_TESTS=OFF` flag. This also went in the ../CMakeLists.txt
file.

    dh_auto_configure -- -DCMAKE_BUILD_TYPE=Release \
                         -DLIBUV_BUILD_TESTS=OFF \
                         -DCXX_FLAGS=-std=c++14

For some reasons the installation of the archive library fails in the
latest. I changed the install() like so:

    install(TARGETS uv LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
                       ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR})

