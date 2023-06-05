# Maintainer: Triss Healy <th at trissyle dot gs>

# IMG_GPU drivers for VisionFive2 RISC-V boards.

pkgname=visionfive2-img-gpu
pkgver=1.17.6210866
pkgrel=4
_tag=VF2_v3.0.4
pkgdesc="This is the GLES and Vulkan implementation provided by StarFive for the IMG_GPU"
url="https://github.com/starfive-tech/soft_3rdpart/tree/JH7110_VisionFive2_devel"
arch=(riscv64)
license=(custom)
provides=(opengl-driver vulkan-driver)
optdepends=('libglvnd: to use opengl'
	    'vulkan-icd-loader: to use vulkan'
	    'ocl-icd: to use opencl')
source=("https://github.com/starfive-tech/soft_3rdpart/raw/${_tag}/IMG_GPU/out/img-gpu-powervr-bin-${pkgver}.tar.gz")
sha256sums=('bb94718c965a1c6d6ee68529e4b85989b08f347ccc8b64d12d8872dd668070d1')
options=(!strip)

package() {
    cd "${srcdir}/img-gpu-powervr-bin-${pkgver}/target"

    # Config files
    install -Dm755 etc/init.d/rc.pvr "${pkgdir}/etc/init.d/rc.pvr"
    install -Dm644 etc/OpenCL/vendors/IMG.icd "${pkgdir}/etc/OpenCL/vendors/IMG.icd"
    install -Dm644 etc/vulkan/icd.d/icdconf.json "${pkgdir}/etc/vulkan/icd.d/icdconf.json"

    # Library files with version
    install -Dm755 usr/lib/libglslcompiler.so.1.17.6210866 "${pkgdir}/usr/lib/libglslcompiler.so.1.17.6210866"
    install -Dm755 usr/lib/libpvr_dri_support.so.1.17.6210866 "${pkgdir}/usr/lib/libpvr_dri_support.so.1.17.6210866"
    install -Dm755 usr/lib/libsrv_um.so.1.17.6210866 "${pkgdir}/usr/lib/libsrv_um.so.1.17.6210866"
    install -Dm755 usr/lib/libsutu_display.so.1.17.6210866 "${pkgdir}/usr/lib/libsutu_display.so.1.17.6210866"
    install -Dm755 usr/lib/libGLESv1_CM_PVR_MESA.so.1.17.6210866 "${pkgdir}/usr/lib/libGLESv1_CM_PVR_MESA.so.1.17.6210866"
    install -Dm755 usr/lib/libPVROCL.so.1.17.6210866 "${pkgdir}/usr/lib/libPVROCL.so.1.17.6210866"
    install -Dm755 usr/lib/libPVRScopeServices.so.1.17.6210866 "${pkgdir}/usr/lib/libPVRScopeServices.so.1.17.6210866"
    install -Dm755 usr/lib/libufwriter.so.1.17.6210866 "${pkgdir}/usr/lib/libufwriter.so.1.17.6210866"
    install -Dm755 usr/lib/libusc.so.1.17.6210866 "${pkgdir}/usr/lib/libusc.so.1.17.6210866"
    install -Dm755 usr/lib/libVK_IMG.so.1.17.6210866 "${pkgdir}/usr/lib/libVK_IMG.so.1.17.6210866"
    install -Dm755 usr/lib/libGLESv2_PVR_MESA.so.1.17.6210866 "${pkgdir}/usr/lib/libGLESv2_PVR_MESA.so.1.17.6210866"

    # Executables
    install -Dm755 usr/local/bin/rgx_triangle_test "${pkgdir}/usr/bin/rgx_triangle_test"
    install -Dm755 usr/local/bin/pvrhtbd "${pkgdir}/usr/bin/pvrhtbd"
    install -Dm755 usr/local/bin/rogue2d_unittest "${pkgdir}/usr/bin/rogue2d_unittest"
    install -Dm755 usr/local/bin/pvrsrvctl "${pkgdir}/usr/bin/pvrsrvctl"
    install -Dm755 usr/local/bin/rgx_compute_test "${pkgdir}/usr/bin/rgx_compute_test"
    install -Dm755 usr/local/bin/pvr_memory_test "${pkgdir}/usr/bin/pvr_memory_test"
    install -Dm755 usr/local/bin/ocl_unit_test "${pkgdir}/usr/bin/ocl_unit_test"
    install -Dm755 usr/local/bin/pvrdebug "${pkgdir}/usr/bin/pvrdebug"
    install -Dm755 usr/local/bin/hwperfbin2jsont "${pkgdir}/usr/bin/hwperfbin2jsont"
    install -Dm755 usr/local/bin/pvrhtb2txt "${pkgdir}/usr/bin/pvrhtb2txt"
    install -Dm755 usr/local/bin/pvr_mutex_perf_test_mx "${pkgdir}/usr/bin/pvr_mutex_perf_test_mx"
    install -Dm755 usr/local/bin/rogue2d_fbctest "${pkgdir}/usr/bin/rogue2d_fbctest"
    install -Dm755 usr/local/bin/rgx_twiddling_test "${pkgdir}/usr/bin/rgx_twiddling_test"
    install -Dm755 usr/local/bin/hwperfjsonmerge.py "${pkgdir}/usr/bin/hwperfjsonmerge.py"
    install -Dm755 usr/local/bin/rgx_blit_test "${pkgdir}/usr/bin/rgx_blit_test"
    install -Dm755 usr/local/bin/ocl_extended_test "${pkgdir}/usr/bin/ocl_extended_test"
    install -Dm755 usr/local/bin/rgx_kicksync_test "${pkgdir}/usr/bin/rgx_kicksync_test"
    install -Dm755 usr/local/bin/pvrtld "${pkgdir}/usr/bin/pvrtld"
    install -Dm755 usr/local/bin/pvrlogsplit "${pkgdir}/usr/bin/pvrlogsplit"
    install -Dm755 usr/local/bin/pvrlogdump "${pkgdir}/usr/bin/pvrlogdump"
    install -Dm755 usr/local/bin/pvrhwperf "${pkgdir}/usr/bin/pvrhwperf"

    # Symbolic links
    cp --no-dereference usr/lib/libPVROCL.so "${pkgdir}/usr/lib/libPVROCL.so"
    cp --no-dereference usr/lib/libVK_IMG.so "${pkgdir}/usr/lib/libVK_IMG.so"
    cp --no-dereference usr/lib/libPVRScopeServices.so "${pkgdir}/usr/lib/libPVRScopeServices.so"
    cp --no-dereference usr/lib/libsutu_display.so "${pkgdir}/usr/lib/libsutu_display.so"
    cp --no-dereference usr/lib/libpvr_dri_support.so "${pkgdir}/usr/lib/libpvr_dri_support.so"
    cp --no-dereference usr/lib/libglslcompiler.so "${pkgdir}/usr/lib/libglslcompiler.so"
    cp --no-dereference usr/lib/libufwriter.so "${pkgdir}/usr/lib/libufwriter.so"
    cp --no-dereference usr/lib/libGLESv1_CM_PVR_MESA.so "${pkgdir}/usr/lib/libGLESv1_CM_PVR_MESA.so"
    cp --no-dereference usr/lib/libGLESv2_PVR_MESA.so "${pkgdir}/usr/lib/libGLESv2_PVR_MESA.so"
    cp --no-dereference usr/lib/libsrv_um.so "${pkgdir}/usr/lib/libsrv_um.so"
    cp --no-dereference usr/lib/libPVROCL.so.1 "${pkgdir}/usr/lib/libPVROCL.so.1"
    cp --no-dereference usr/lib/libGLESv1_CM.so.1 "${pkgdir}/usr/lib/libGLESv1_CM.so.1"
    cp --no-dereference usr/lib/libGLESv1_CM.so "${pkgdir}/usr/lib/libGLESv1_CM.so"
    cp --no-dereference usr/lib/libVK_IMG.so.1 "${pkgdir}/usr/lib/libVK_IMG.so.1"
    cp --no-dereference usr/lib/libusc.so "${pkgdir}/usr/lib/libusc.so"

    # Firmware files
    install -Dm644 lib/firmware/rgx.fw.36.50.54.182 "${pkgdir}/lib/firmware/rgx.fw.36.50.54.182"
    install -Dm644 lib/firmware/rgx.sh.36.50.54.182 "${pkgdir}/lib/firmware/rgx.sh.36.50.54.182"
}
