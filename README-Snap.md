
# Source

I get the files from the github.com releases.

https://github.com/libuv/libuv/releases

# Changes

Very minimal at this time. I tried to turn off the tests from our
CMakeLists.txt but that's useless on LaunchPad. So instead we want
to comment out the following line in the main CMakeLists.txt

    #include(CTest)


