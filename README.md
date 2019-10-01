# tmp-cip-xilinx-mpsoc
temporal repository to share locally developed cip tree for mpsoc

This repository is intended to share the latest outcome of the work which was locally done by Cybertrust to experiment to merge MPSoC code to CIP tree.

The current status is that Cybertrust identified patches (in BSP) to be applied to CIP SLTS4.19 for some use cases.

Please note that those patches were in BSP, and our next step is to figure out which patches are actually in Mainline tree. In another word, some of the current identified patches may not be in Mainline tree, yet.

The following files need to be combined to linux-4.19.56.tar.bz2 .
```
 linux-4.19.56.tar.bz2.001
 linux-4.19.56.tar.bz2.002
 linux-4.19.56.tar.bz2.003
 linux-4.19.56.tar.bz2.004
 linux-4.19.56.tar.bz2.005
 linux-4.19.56.tar.bz2.006
 linux-4.19.56.tar.bz2.007
 ```

After expanding linux-4.19.56.tar.bz2, the output of "git status" should be like the following.
```
---------------------------------------------------------
Changes not staged for commit:
        modified:   Documentation/devicetree/bindings/soc/xilinx/xlnx,vcu.txt
        modified:   Documentation/media/uapi/v4l/subdev-formats.rst
        modified:   MAINTAINERS
        modified:   arch/arm/boot/dts/zynq-zturn.dts
        modified:   arch/arm/mach-zynq/Makefile
        modified:   arch/arm/mach-zynq/common.h
        modified:   arch/arm/mach-zynq/pm.c
        modified:   arch/arm/mach-zynq/slcr.c
        modified:   arch/arm64/Kconfig.platforms
        modified:   arch/arm64/boot/dts/xilinx/Makefile
        modified:   arch/arm64/boot/dts/xilinx/zynqmp-clk.dtsi
        modified:   arch/arm64/boot/dts/xilinx/zynqmp-zc1232-revA.dts
        modified:   arch/arm64/boot/dts/xilinx/zynqmp-zc1254-revA.dts
        modified:   arch/arm64/boot/dts/xilinx/zynqmp-zc1275-revA.dts
        modified:   arch/arm64/boot/dts/xilinx/zynqmp-zc1751-xm015-dc1.dts
        modified:   arch/arm64/boot/dts/xilinx/zynqmp-zc1751-xm016-dc2.dts
        modified:   arch/arm64/boot/dts/xilinx/zynqmp-zc1751-xm017-dc3.dts
        modified:   arch/arm64/boot/dts/xilinx/zynqmp-zc1751-xm018-dc4.dts
        modified:   arch/arm64/boot/dts/xilinx/zynqmp-zc1751-xm019-dc5.dts
        modified:   arch/arm64/boot/dts/xilinx/zynqmp-zcu100-revC.dts
        modified:   arch/arm64/boot/dts/xilinx/zynqmp-zcu102-revA.dts
        modified:   arch/arm64/boot/dts/xilinx/zynqmp-zcu102-revB.dts
        modified:   arch/arm64/boot/dts/xilinx/zynqmp-zcu104-revA.dts
        modified:   arch/arm64/boot/dts/xilinx/zynqmp-zcu106-revA.dts
        modified:   arch/arm64/boot/dts/xilinx/zynqmp-zcu111-revA.dts
        modified:   arch/arm64/boot/dts/xilinx/zynqmp.dtsi
        modified:   drivers/clk/Kconfig
        modified:   drivers/clk/Makefile
        modified:   drivers/clk/clk-fixed-factor.c
        modified:   drivers/clk/clk.c
        modified:   drivers/clk/zynq/clkc.c
        modified:   drivers/dma/Kconfig
        modified:   drivers/dma/xilinx/Makefile
        modified:   drivers/firmware/Kconfig
        modified:   drivers/firmware/Makefile
        modified:   drivers/gpio/gpio-xilinx.c
        modified:   drivers/gpio/gpio-zynq.c
        modified:   drivers/gpio/gpiolib.c
        modified:   drivers/gpu/drm/Kconfig
        modified:   drivers/gpu/drm/Makefile
        modified:   drivers/gpu/drm/drm_fb_cma_helper.c
        modified:   drivers/gpu/drm/drm_fourcc.c
        modified:   drivers/gpu/drm/drm_framebuffer.c
        modified:   drivers/i2c/busses/i2c-cadence.c
        modified:   drivers/i2c/busses/i2c-xiic.c
        modified:   drivers/media/platform/xilinx/Kconfig
        modified:   drivers/media/platform/xilinx/Makefile
        modified:   drivers/media/platform/xilinx/xilinx-dma.c
        modified:   drivers/nvmem/Kconfig
        modified:   drivers/nvmem/Makefile
        modified:   drivers/phy/Kconfig
        modified:   drivers/phy/Makefile
        modified:   drivers/pinctrl/Kconfig
        modified:   drivers/pinctrl/Makefile
        modified:   drivers/reset/Makefile
        modified:   drivers/soc/xilinx/Kconfig
        modified:   drivers/soc/xilinx/Makefile
        modified:   drivers/soc/xilinx/xlnx_vcu.c
        modified:   drivers/spi/Kconfig
        modified:   drivers/spi/Makefile
        modified:   drivers/spi/spi-zynqmp-gqspi.c
        modified:   drivers/staging/Kconfig
        modified:   drivers/staging/Makefile
        modified:   include/drm/drm_fourcc.h
        modified:   include/dt-bindings/media/xilinx-vip.h
        modified:   include/dt-bindings/phy/phy.h
        modified:   include/linux/clk-provider.h
        modified:   include/linux/clk/zynq.h
        modified:   include/linux/gpio/driver.h
        modified:   include/uapi/drm/drm_fourcc.h
        modified:   include/uapi/drm/drm_mode.h
        modified:   include/uapi/linux/media-bus-format.h
        modified:   sound/soc/Kconfig
        modified:   sound/soc/Makefile

Untracked Files:
        Documentation/ABI/stable/sysfs-firmware-zynqmp
        Documentation/devicetree/bindings/clock/xlnx,versal-clk.txt
        Documentation/devicetree/bindings/display/xlnx/
        Documentation/devicetree/bindings/drm/
        Documentation/devicetree/bindings/firmware/xilinx/
        Documentation/devicetree/bindings/phy/phy-zynqmp.txt
        Documentation/devicetree/bindings/power/xlnx,zynqmp-genpd.txt
        Documentation/devicetree/bindings/reset/xlnx,zynqmp-reset.txt
        arch/arm/mach-zynq/suspend.S
        arch/arm64/boot/dts/xilinx/zynqmp-clk-ccf.dtsi
        arch/arm64/boot/dts/xilinx/zynqmp-zc1275-revB.dts
        arch/arm64/boot/dts/xilinx/zynqmp-zc1285-revA.dts
        arch/arm64/boot/dts/xilinx/zynqmp-zcu104-revC.dts
        arch/arm64/configs/xilinx_zynqmp_defconfig
        drivers/clk/clk-si5324.c
        drivers/clk/clk-si5324.h
        drivers/clk/idt/
        drivers/clk/si5324.h
        drivers/clk/si5324drv.c
        drivers/clk/si5324drv.h
        drivers/clk/zynqmp/
        drivers/dma/xilinx/Kconfig
        drivers/dma/xilinx/axidmatest.c
        drivers/dma/xilinx/cdmatest.c
        drivers/dma/xilinx/vdmatest.c
        drivers/dma/xilinx/xilinx_dpdma.c
        drivers/dma/xilinx/xilinx_frmbuf.c
        drivers/dma/xilinx/xilinx_ps_pcie.h
        drivers/dma/xilinx/xilinx_ps_pcie_dma_client.c
        drivers/dma/xilinx/xilinx_ps_pcie_main.c
        drivers/dma/xilinx/xilinx_ps_pcie_platform.c
        drivers/firmware/xilinx/
        drivers/gpu/drm/xilinx/
        drivers/gpu/drm/xlnx/
        drivers/media/platform/xilinx/xilinx-vpss-csc.c
        drivers/media/platform/xilinx/xilinx-vpss-scaler.c
        drivers/nvmem/zynqmp_nvmem.c
        drivers/phy/phy-zynqmp.c
        drivers/pinctrl/pinctrl-zynqmp.c
        drivers/reset/reset-zynqmp.c
        drivers/soc/xilinx/xlnx_vcu_clk.c
        drivers/soc/xilinx/xlnx_vcu_core.c
        drivers/soc/xilinx/zynqmp/
        drivers/soc/xilinx/zynqmp_pm_domains.c
        drivers/soc/xilinx/zynqmp_power.c
        drivers/spi/spi-zynq-qspi.c
        drivers/staging/apf/
        drivers/staging/fclk/
        include/dt-bindings/clock/xlnx-versal-clk.h
        include/dt-bindings/clock/xlnx-zynqmp-clk.h
        include/dt-bindings/drm/
        include/dt-bindings/pinctrl/pinctrl-zynqmp.h
        include/dt-bindings/power/xlnx-versal-power.h
        include/dt-bindings/power/xlnx-zynqmp-power.h
        include/dt-bindings/reset/xlnx-zynqmp-resets.h
        include/linux/dma/xilinx_frmbuf.h
        include/linux/dma/xilinx_ps_pcie_dma.h
        include/linux/firmware/xlnx-zynqmp.h
        include/linux/phy/phy-zynqmp.h
        include/linux/soc/xilinx/
        include/soc/xilinx/
        sound/soc/xilinx/
---------------------------------------------------------
```

