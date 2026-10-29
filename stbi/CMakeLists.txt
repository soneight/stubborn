cmake_minimum_required( VERSION 3.8...3.27 )
project( stbi VERSION 2.30 )
set( LIB_SON8 ${PROJECT_NAME}__son8 )
# options
option( STBI_SON8_HEADER_ONLY "Build as header-only (interface) library" OFF )
# -- image formats, NOTE: png is always enabled
option( STBI_SON8_ENABLE_JPG "Enable `jpg` file format" OFF )
option( STBI_SON8_ENABLE_BMP "Enable `bmp` file format" OFF )
option( STBI_SON8_ENABLE_PSD "Enable `psd` file format" OFF )
option( STBI_SON8_ENABLE_TGA "Enable `tga` file format" OFF )
option( STBI_SON8_ENABLE_GIF "Enable `gif` file format" OFF )
option( STBI_SON8_ENABLE_HDR "Enable `hdr` file format" OFF )
option( STBI_SON8_ENABLE_PIC "Enable `pic` file format" OFF )
option( STBI_SON8_ENABLE_PNM "Enable `pnm` file format" OFF )

add_subdirectory( source )
add_library( ${PROJECT_NAME}::son8 ALIAS ${LIB_SON8} )

if ( STBI_SON8_HEADER_ONLY )
    target_include_directories( ${LIB_SON8} INTERFACE include )
else( )
    target_include_directories( ${LIB_SON8} PUBLIC include )
endif( )

# Apache License 2.0
# NO WARRANTY OF ANY KIND see <http://www.apache.org/licenses/LICENSE-2.0>
# SPDX-License-Identifier: Apache-2.0
# lib: `stubborn` C++17 STB Image Wrapper
# Ⓒ Copyright (c) 2026 Oleg'Ease'Kharchuk ᦒ
