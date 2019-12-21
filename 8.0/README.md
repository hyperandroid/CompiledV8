This version of v8 for android has been compiled using monolith option.
Previous versions' fat libraries where created by hand.
This version needs the default ndk custom libcxx flag, otherwise allocators will fail miserably.

It is important to note that NDK compilation has been changed too. This file:

v8/buildtools/third_party/libc++/trunk/include/__config

has been made this change:

_LIBCPP_CONCAT(__,_LIBCPP_ABI_VERSION) => _LIBCPP_CONCAT(__ndk,_LIBCPP_ABI_VERSION)

this sets default NDK stdlib prefix so linker does not complaint.
