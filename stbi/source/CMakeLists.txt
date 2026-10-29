if ( STBI_SON8_HEADER_ONLY )
    add_library( ${LIB_SON8} INTERFACE )
else( )
    add_library( ${LIB_SON8} )
    target_sources( ${LIB_SON8} PRIVATE stb_image.c )

    if ( NOT STBI_SON8_ENABLE_JPG )
        target_compile_definitions( ${LIB_SON8} PRIVATE STBI_NO_JPEG )
    endif( )

    set( STBI_SON8_IMAGE_FORMATS BMP PSD TGA GIF HDR PIC PNM )
    foreach( FMT IN LISTS STBI_SON8_IMAGE_FORMATS )
        if ( NOT STBI_SON8_ENABLE_${FMT} )
            target_compile_definitions( ${LIB_SON8} PRIVATE STBI_NO_${FMT} )
        endif( )
    endforeach( )
endif( )

# Apache License 2.0
# NO WARRANTY OF ANY KIND see <http://www.apache.org/licenses/LICENSE-2.0>
# SPDX-License-Identifier: Apache-2.0
# lib: `stubborn` C++17 STB Image Wrapper
# Ⓒ Copyright (c) 2026 Oleg'Ease'Kharchuk ᦒ
