# Copyright (c) 2006, 2010, Oracle and/or its affiliates. All rights reserved.
# Copyright (c) 2022 Huawei Technologies Co., Ltd.
# 
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; version 2 of the License.
# 
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
# 
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 51 Franklin St, Fifth Floor, Boston, MA  02110-1301 USA

ADD_COMPILE_DEFINITIONS(
  COMPILE_DEFINITIONS MYSQL_DYNAMIC_PLUGIN)

# 添加头文件路径，确保包含 rapidjson 目录
INCLUDE_DIRECTORIES(
  ${CMAKE_SOURCE_DIR}/include
  ${CMAKE_SOURCE_DIR}/plugin
  ${CMAKE_SOURCE_DIR}/extra/
  ${CMAKE_SOURCE_DIR}/sql
  ${CMAKE_SOURCE_DIR}/extra/rapidjson/include
)

add_compile_options(-fpermissive)

MYSQL_ADD_PLUGIN(thread_pool
  threadpool_common.cc
  threadpool_unix.cc
  MODULE_ONLY
  MODULE_OUTPUT_NAME "thread_pool"
  )

ADD_COMPILE_DEFINITIONS(
  COMPILE_DEFINITIONS MYSQL_DYNAMIC_PLUGIN)
