This version of v8 for android has been compiled using monolith option.
Previous versions' fat libraries where created by hand.
It is important to note that NDK compilation has been changed too. This file:

`v8/buildtools/third_party/libc++/trunk/include/__config`

has been made this change:

`_LIBCPP_CONCAT(__,_LIBCPP_ABI_VERSION)` => `_LIBCPP_CONCAT(__ndk,_LIBCPP_ABI_VERSION)`

this sets default NDK stdlib prefix so linker does not complaint.

Also, this version has the isolate log disabled.
I got a crash when initializing the log in the 3 archs.
Everyday is a mistery when compiling v8.

The zip file includes libraries and header files.