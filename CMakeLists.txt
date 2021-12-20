project (stb_image_clone)

cmake_minimum_required (VERSION 3.1)
set (CMAKE_CXX_STANDARD 11)

set (HEADER_FILES
     stb_image.h
     stb_image_write.h
    )

set (IMPL_FILES
     stb_image.cpp
     )

set (SOURCE_FILES ${HEADER_FILES} ${IMPL_FILES})

# ------------------------------------------------------------------------------

add_library (stb_image_clone STATIC ${SOURCE_FILES})

# ------------------------------------------------------------------------------

# To treat warning as error, uncomment the following:
if (MSVC)
   target_compile_options (stb_image_clone PRIVATE /W4 /WX)
else ()
#   target_compile_options (stb_image_clone PRIVATE -Wall -Wextra -Wpedantic -Werror)
endif ()