# CMake buildscript for CUnit - Build CUnit with a CMake buildscript.
# Copyright (C) 2016 - Christian Verhalen
#
# This library is free software; you can redistribute it and/or
# modify it under the terms of the GNU Library General Public
# License as published by the Free Software Foundation;.
#
# This library is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
# Library General Public License for more details.
#
# You should have received a copy of the GNU Library General Public
# License along with this library; if not, write to the Free Software
# Foundation, Inc., 59 Temple Place, Suite 330, Boston, MA  02111-1307  USA
#
cmake_minimum_required (VERSION 2.8)

project (cunit)

include_directories (
    CUnit/Headers
)

set (source_files
    CUnit/Sources/Automated/Automated.c
    CUnit/Sources/Basic/Basic.c
    CUnit/Sources/Console/Console.c
    CUnit/Sources/Framework/CUError.c
    CUnit/Sources/Framework/TestDB.c
    CUnit/Sources/Framework/TestRun.c
    CUnit/Sources/Framework/Util.c
)

add_library (${CMAKE_PROJECT_NAME} ${source_files})

install(TARGETS ${CMAKE_PROJECT_NAME} DESTINATION .)
install(DIRECTORY CUnit/Headers/ DESTINATION . FILES_MATCHING PATTERN "*.h")
