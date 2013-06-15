cmake_minimum_required(VERSION 2.8)

SET(PRJ dpdk-l2fwd)
PROJECT(${PRJ})
SET(SOURCE_EXE main.c)

INCLUDE_DIRECTORIES($ENV{DPDK_INCLUDE})
LINK_DIRECTORIES($ENV{DPDK_LIBRARIES})

ADD_EXECUTABLE(${PRJ} ${SOURCE_EXE})
TARGET_LINK_LIBRARIES(${PRJ} ethdev rte_eal rte_lpm rte_mbuf rte_pmd_igb rte_cmdline rte_hash rte_malloc rte_mempool rte_ring rte_pmd_ixgbe rte_timer)
TARGET_LINK_LIBRARIES(${PRJ} pthread dl rt)