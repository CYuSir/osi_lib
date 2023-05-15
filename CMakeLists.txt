cmake_minimum_required(VERSION 3.10.0)
# 设置工程名称和版本
project(osi VERSION 1.0.0)

# 设置 C++ 标准为 C++14
set(CMAKE_CXX_STANDARD 14)

# 添加 include 目录
include_directories(include)

# 添加源文件
set(SOURCES
    src/alarm.cc
    src/allocation_tracker.cc
    src/allocator.cc
    src/config.cc
    src/fixed_queue.cc
    src/future.cc
    src/hash_functions.cc
    src/hash_map.cc
    src/list.cc
    src/reactor.cc
    src/semaphore.cc
    src/thread.cc
)

# 生成 osi 动态库
add_library(osi SHARED ${SOURCES})

# 安装规则
install(TARGETS osi DESTINATION lib)
install(DIRECTORY include/ DESTINATION include/)