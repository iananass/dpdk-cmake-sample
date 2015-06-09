cmake_minimum_required(VERSION 2.8)

SET(PRJ dpdk2fwd)
PROJECT(${PRJ})
SET(SOURCE_EXE main.c)

INCLUDE_DIRECTORIES($ENV{DPDK_PATH}/include)
LINK_DIRECTORIES($ENV{DPDK_PATH}/lib)

ADD_DEFINITIONS(-mssse3 -D__STDC_LIMIT_MACROS)
SET( DPDK_LIB  "-Wl,--whole-archive -lrte_mbuf  -lrte_eal -lrte_pmd_e1000 -lrte_mempool -lrte_ring -lethdev -lrte_pmd_ixgbe -lrte_malloc -Wl,--no-whole-archive" )

ADD_EXECUTABLE(${PRJ} ${SOURCE_EXE})
TARGET_LINK_LIBRARIES(${PRJ} ${DPDK_LIB})
TARGET_LINK_LIBRARIES(${PRJ} pthread dl rt)