# Changelog
All notable changes to VOLK will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html), starting with version 2.0.0.


## [2.0.0] - 2019-08-06

This is the first version to use semantic versioning. It starts the logging of changes.


## [2.0.0] - 2019-11-10

Albin Stigo (6):
      Adds toolchain file for Raspberry Pi 3 and updates Raspberry 4 toolchain file
      CMAKE_ASM_FLAGS should be set in the toolchain file
      Adds CMAKE_ASM_FLAGS to arm toolchain files
      adds neonv7 for volk_16ic_magnitude_16i
      Adds neonv7 to volk_32fc_index_max_32u
      Adds neonv7 for volk_32fc_s32f_power_spectrum_32f

Amr Bekhit (2):
      Fix liborc headers not found on Ubuntu server. When compiling Volk on Ubuntu server 19.10 for the Raspberry Pi, CMake is unable to find the liborc header files despite them being installed. This patch fixes this issue by providing PATH_SUFFIXES allowing CMake to find the headers.
      Simplified FIND_PATH

Christoph Mayer (20):
      fix for different results of SIMD kernels w.r.t. generic kernel
      fix for flaky kernel volk_32f_log2_32f
      call the generic kernel for the remaining iterations in SIMD
      call the generic kernel for the remaining iterations in SIMD
      same order of FP additions in (non-NEON) SIMD kernels as in the generic kernel volk_32f_x3_sum_of_poly_32f
      fix for spurious heap buffer overflow
      cosmetics; shorter sse3 implementations applying the same fix used for the AVX implementations to the SSE3 allows to get rid of the tail of the SSE3 implementations which seems to have been there in order to avoid the problem found for the AVX kernels.
      bug fixes for volk_32f_index_max_{16,32}u
      more transparent logic (CMT_LE -> CMP_GT)
      use named predicates in _mm256_cmp_ps
      make non-IEEE log2f behaviour clear
      fix for volk_32f_8u_polarbutterflypuppet_32f
      volk_8u_conv_k7_r2puppet_8u: initialize decisions to zero
      one statement per line (volk_32fc_convert_16ic)
      volk_32fc_s32f_magnitude_16i MSVC
      VOLK C++ allocator and C++11 std::vector type alias added
      rename volk_alloc.h to volk_alloc.hh
      use constants defined in stdint.h in volk_32f_s32f_convert_{8,16,32}i
      volatile -> __VOLK_VOLATILE
      32768 -> SHRT_MAX in volk_16ic_magnitude_16i

Clayton Smith (3):
      Fix AVX FMA rotator
      Fail tests if non-numbers are detected
      Use sensible scalars for rotator and power

Damian Miralles (6):
      proto-kernel: Adds NEONv8 protokernel to volk_32f_64f_add_64f
      proto-kernel Adds Neonv8 support for volk_32fc_deinterleave_64f_x2.
      protokernel: Adds Neonv8 support for 32fc_deinterleave_64f_x2 and 32fc_deinterleave_real_64f
      Update arm_cortex_a72_hardfp_native.cmake
      Update arm_cortex_a72_hardfp_native.cmake
      Update volk_32f_64f_add_64f.h

Johannes Demel (3):
      cmake: bump minimum version to 3.8
      cmake: remove obsolete cmake version checks
      configpath: Abort read/write if path not found

Michael Dickens (27):
      Merge pull request #278 from argilo/fix-rotator
      Merge pull request #287 from hcab14/fix_volk_32f_x3_sum_of_poly_32f
      Merge pull request #289 from hcab14/fix_volk_32f_index_max
      Merge pull request #285 from hcab14/fix_volk_32fc_s32f_magnitude_16i
      Merge pull request #274 from ast/volk_16ic_magnitude_16i_neonv7
      Merge pull request #276 from ast/volk_32fc_index_max_32u
      Merge pull request #277 from ast/volk_32fc_s32f_power_spectrum_32f
      Merge pull request #288 from hcab14/fix_volk_8u_x3_encodepolarpuppet_8u
      Merge pull request #271 from ast/rbpi_3_and_4_toolchains
      Merge pull request #258 from luzpaz/misc-typos
      Merge pull request #273 from balister/toolchain-stuff
      Merge pull request #293 from hcab14/cmp_ps_predicates
      Merge pull request #295 from hcab14/fix_volk_32f_8u_polarbutterflypuppet_32f
      Merge pull request #294 from hcab14/fix_volk_8u_conv_k7_r2puppet_8u
      Merge pull request #280 from jdemel/bump-cmake-min-version
      Merge pull request #286 from hcab14/fix_volk_32f_log2_32f
      Merge pull request #296 from hcab14/fix_volk_32fc_convert_16ic
      Merge pull request #297 from hcab14/fix_volk_32fc_s32f_magnitude_16i_MSVC
      Merge pull request #284 from hcab14/master
      Merge pull request #298 from hcab14/fix_volk_32f_s32f_convert_add_limits_h
      Merge pull request #299 from hcab14/fix_volk_32fc_s32f_magnitude_16i_MSVC
      Add __clang__ specific attributes
      Merge pull request #283 from dmiralles2009/neon_32fc_deinterleave
      Merge pull request #302 from michaelld/add_clang_attributes
      Merge pull request #282 from dmiralles2009/neon_32f_64f_add
      Merge pull request #303 from amrbekhit/fix-liborc-notfound
      Merge pull request #305 from jdemel/no-config-path

Philip Balister (1):
      Update asm flag handing for arm-linux-gnueabihf.cmake toolchain.

hcab14 (2):
      fix for volk_32fc_convert_16ic (NEON)
      added a NEONv8 version of volk_32fc_convert_16ic

luz.paz (1):
      Misc. typos
