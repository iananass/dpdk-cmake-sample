cmake_minimum_required(VERSION 2.8)

SET(PRJ dpdk2fwd)
PROJECT(${PRJ})
SET(SOURCE_EXE main.c)

INCLUDE_DIRECTORIES($ENV{DPDK_PATH}/include)
LINK_DIRECTORIES($ENV{DPDK_PATH}/lib)

ADD_EXECUTABLE(${PRJ} ${SOURCE_EXE})
TARGET_LINK_LIBRARIES(${PRJ} ethdev rte_sched  rte_mbuf rte_eal rte_lpm rte_cmdline rte_hash rte_malloc rte_mempool rte_ring rte_pmd_ring  rte_pmd_e1000 rte_pmd_ixgbe rte_timer)
TARGET_LINK_LIBRARIES(${PRJ} pthread dl rt)