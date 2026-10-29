cmake_minimum_required( VERSION 3.8...3.27 )
project( stubborn VERSION 0.0.0 LANGUAGES CXX )
set( SON8_LIB son8__${PROJECT_NAME} )
# private configuration under source directory
add_subdirectory( source )
add_library( son8::${PROJECT_NAME} ALIAS ${SON8_LIB} )
target_compile_features( ${SON8_LIB} INTERFACE cxx_std_17 )
target_compile_options( ${SON8_LIB} INTERFACE $<$<CXX_COMPILER_ID:MSVC>:/utf-8 /permissive- /Zc:__cplusplus> )
target_include_directories( ${SON8_LIB} INTERFACE include )

# Apache License 2.0
# NO WARRANTY OF ANY KIND see <http://www.apache.org/licenses/LICENSE-2.0>
# SPDX-License-Identifier: Apache-2.0
# lib: `stubborn` C++17 STB Image Wrapper
# Ⓒ Copyright (c) 2026 Oleg'Ease'Kharchuk ᦒ
