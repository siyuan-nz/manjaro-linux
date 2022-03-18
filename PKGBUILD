# AArch64 multi-platform
# Maintainer: Dan Johansen <strit@manjaro.org>
# Contributor: Kevin Mihelich <kevin@archlinuxarm.org>
# Contributor: Dragan Simic <dsimic@buserror.io>

pkgbase=linux
_srcname=linux-5.16
_kernelname=${pkgbase#linux}
_desc="AArch64 multi-platform"
pkgver=5.16.15
pkgrel=2
arch=('aarch64')
url="http://www.kernel.org/"
license=('GPL2')
makedepends=('xmlto' 'docbook-xsl' 'kmod' 'inetutils' 'bc' 'git' 'dtc')
options=('!strip')
source=("http://www.kernel.org/pub/linux/kernel/v5.x/${_srcname}.tar.xz"
        "http://www.kernel.org/pub/linux/kernel/v5.x/patch-${pkgver}.xz"
        '1001-arm64-dts-allwinner-add-hdmi-sound-to-pine-devices.patch'
        '1002-arm64-dts-allwinner-add-ohci-ehci-to-h5-nanopi.patch'
        '1003-drm-bridge-analogix_dp-Add-enable_psr-param.patch'                   # From list: https://patchwork.kernel.org/project/dri-devel/patch/20200626033023.24214-2-shawn@anastas.io/
        '1004-gpu-drm-add-new-display-resolution-2560x1440.patch'
        '1005-panfrost-Silence-Panfrost-gem-shrinker-loggin.patch'
        '1006-arm64-dts-rockchip-Add-Firefly-Station-p1-support.patch'
        '1007-drm-rockchip-add-support-for-modeline-32MHz-e.patch'
        '1008-rk3399-rp64-pcie-Reimplement-rockchip-PCIe-bus-scan-delay.patch'
        '1009-drm-meson-add-YUV422-output-support.patch'
        '1010-arm64-dts-meson-add-initial-Beelink-GT1-Ultimate-dev.patch'
        '1011-add-dts-meson-g12b-ugoos-am6-plus.patch'
        '1012-drm-panfrost-scheduler-improvements.patch'                           # Will be submitted upstream by the author
        '1013-arm64-dts-rockchip-Add-PCIe-bus-scan-delay-to-RockPr.patch'
        '1014-drm-rockchip-support-gamma-control-on-RK3399.patch'                  # From list: https://patchwork.kernel.org/project/linux-arm-kernel/cover/20211019215843.42718-1-sigmaris@gmail.com/
        '1015-media-rockchip-rga-do-proper-error-checking-in-probe.patch'          # From list: https://patchwork.kernel.org/project/linux-rockchip/patch/20211120122321.20253-1-kmcopper@danwin1210.me/
        '1016-arm-dts-rockchip-firefly-station-m2.patch'
        '1017-add-dts-rk3568-station-p2.patch'
        '1018-add-dts-rk3568-radxa-rock3a.patch'
        '1019-arm64-dts-rockchip-switch-to-hs200-on-rockpi4.patch'                 # Temporary hotfix, not for upstreaming
        '1020-arm64-dts-meson-remove-CPU-opps-below-1GHz-for-G12B-boards.patch'    # From list: https://patchwork.kernel.org/project/linux-amlogic/patch/20220210100638.19130-2-christianshewitt@gmail.com/
        '1021-arm64-dts-meson-remove-CPU-opps-below-1GHz-for-SM1-boards.patch'     # From list: https://patchwork.kernel.org/project/linux-amlogic/patch/20220210100638.19130-3-christianshewitt@gmail.com/
        '1022-arm64-dts-rockchip-Add-PCIe-bus-scan-delay-to-Rock-P.patch'
        '2001-Bluetooth-Add-new-quirk-for-broken-local-ext-features.patch'         # From list: https://patchwork.kernel.org/project/bluetooth/patch/20200705195110.405139-2-anarsoul@gmail.com/
        '2002-Bluetooth-btrtl-add-support-for-the-RTL8723CS.patch'                 # From list: https://patchwork.kernel.org/project/bluetooth/patch/20200705195110.405139-3-anarsoul@gmail.com/
        '2003-arm64-allwinner-a64-enable-Bluetooth-On-Pinebook.patch'              # From list: https://patchwork.kernel.org/project/bluetooth/patch/20200705195110.405139-4-anarsoul@gmail.com/
        '2004-arm64-dts-allwinner-enable-bluetooth-pinetab-pinepho.patch'          # PinePhone part is in linux-next
        '2005-staging-add-rtl8723cs-driver.patch'                                  # Not upstreamable
        '2006-arm64-dts-allwinner-pinetab-add-accelerometer.patch'
        '2007-arm64-dts-allwinner-pinetab-enable-jack-detection.patch'
        '2008-Bluetooth-Read-codec-capabilities-only-if-supported.patch'           # From https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=107fe0482b549a0e (applied in linux-rc 5.17-rc1)
        '2009-btsdio-Do-not-bind-to-non-removable-BCM4345-and-BCM43455.patch'      # From https://lore.kernel.org/all/20211020130023.196651-1-kmcopper@danwin1210.me/t/ (applied to bluetooth-next and 5.17-rc)
        '2010-brcmfmac-USB-probing-provides-no-board-type.patch'                   # Will be submitted upstream by the author
        '2011-dts-rockchip-Adapt-and-adopt-Type-C-support-from-Pin.patch'          # Not upstreamable
        '3172-arm64-dts-rk3399-pinebook-pro-Fix-USB-PD-charging.patch'             # Third set of patches: START
        '3174-arm64-dts-rk3399-pinebook-pro-Improve-Type-C-support.patch'          # All patches in the third set are from https://xff.cz/kernels/5.16/patches/
        '3176-arm64-dts-rk3399-pinebook-pro-Remove-redundant-pinct.patch'          # See the prepare() function below for more details
        '3376-drm-rockchip-cdn-dp-Disable-CDN-DP-on-disconnect.patch'
        '3392-usb-typec-fusb302-Set-the-current-before-enabling-pu.patch'
        '3396-usb-typec-fusb302-Update-VBUS-state-even-if-VBUS-int.patch'
        '3398-usb-typec-fusb302-Add-OF-extcon-support.patch'
        '3399-usb-typec-fusb302-Fix-register-definitions.patch'
        '3400-usb-typec-fusb302-Clear-interrupts-before-we-start-t.patch'
        '3401-usb-typec-typec-extcon-Add-typec-extcon-bridge-drive.patch'
        '3402-phy-rockchip-typec-Make-sure-the-plug-orientation-is.patch'
        '3457-phy-rockchip-inno-usb2-More-robust-charger-detection.patch'
        '3458-usb-typec-extcon-Don-t-touch-charger-proprties.patch'
        '3459-arm64-dts-rk3399-pinebook-pro-Don-t-allow-usb2-phy-d.patch'          # Third set of patches: END
        'config'
        'linux.preset'
        '60-linux.hook'
        '90-linux.hook')
md5sums=('e6680ce7c989a3efe58b51e3f3f0bf93'
         '2728ee431a8e0192b9a7806033f07332'
         '9aa0591c2d601a104d664a802a44728c'
         'e6fe272dc95a1c0a8f871924699fea16'
         '9f27b2a05eaeb1995fc0fcf6a8b923c4'
         '6f592c11f6adc1de0f06e5d18f8c2862'
         'f8f0b124c741be61d86bea8d44e875f9'
         '564136ab1c75b6dc67be02b54e695ae5'
         '66fae3fc96f0a478a56ff11632f3ef70'
         '245858f26512dfc48adbf509b6fc8364'
         '469417b64e6a2bf65bd74c6d9cad2040'
         '8f4816a1ed98f80eebad49b6446427a9'
         '1b92d7617e60d3c525a4b18ab4351185'
         '140b727650029bf2d99f2d176f0876d8'
         '28982d87c45ed8f5aab966d82f8455d8'
         '19e2279811700cd8aa4ab326603d2f61'
         '72030cbfe655fc94b28ea289ee3a53a8'
         '7b23ad49405f14618cfd92f59c25b911'
         '0ef7f4e1e2e87797be664541ad33e464'
         '516a0c0f0dc663419ed275b94edbab55'
         'a0f649f78c857a01e1680b89b58b05eb'
         '5f88754771166cd2d95d7bc3911cacca'
         'ee8eb5a23404c879fcfd09e5b7c124b8'
         'a0cf3209d3f856522ef14c4618837ae7'
         '372260658bc5fe55ee9b5690d8f67cb9'
         'a100d32aa6c345290061d2a773bf1232'
         '9510821113c122f91f47b9d0f7ca7264'
         'a74fcfa1e085a3a99dcf4f214c1ca65a'
         '959c2cb33566b27f880c178039d6c12f'
         'd0fd6bd627223d4c9fc001ffff9df401'
         'f79300740a7350d2d24ab5e120831b52'
         'faecd80e9d0727d360aa7bbe28b53489'
         '6b42e61f8ef7cc9ebab731a71fd45e1a'
         'd2654df7fc87e5c874505a2d98cbce1c'
         '4526b864558d806407125e51b8464c65'
         'c9a0b350984c9bf777c76958e1199521'
         'e62b2fd8f3ecf6e5ef90b4bc6b91f2c7'
         '91bfa4c046b12158d506391fbb1ce78b'
         '4c997da4f50ce6033a8f560b5f660e49'
         '5f68f0692f74d3303f30d62956f8eb22'
         '3a5e257ce5a8b3a36c4bd403cb7fcaf9'
         '9c96de7df3153ee619d1badb894a5eec'
         '2a2ea20836777c460580c667ae64dec5'
         '000ee88e0305d92a437c9eafb5ae470b'
         'ca36e55d9edf0e0f0ffd7ab2805b054d'
         '0200f352c6649e95754a6b99068fc4ab'
         '571600f947152c0a473b79df2fcf3994'
         'e08b712dece0abbbf7c5fbc797d20fbc'
         '1f16fa03ed64f0a0ec207b0cacb4b123'
         '980556b691b2fe8988b0c9f7259c5044'
         '86d4a35722b5410e3b29fc92dae15d4b'
         'ce6c81ad1ad1f8b333fd6077d47abdaf'
         '3dc88030a8f2f5a5f97266d99b149f77')

prepare() {
  cd ${_srcname}

  # Apply the minor version patch
  patch -Np1 -i "${srcdir}/patch-${pkgver}"

  # Assorted ALARM patches

  # Assorted Manjaro ARM patches
  patch -Np1 -i "${srcdir}/1001-arm64-dts-allwinner-add-hdmi-sound-to-pine-devices.patch"            # Pine64
  patch -Np1 -i "${srcdir}/1002-arm64-dts-allwinner-add-ohci-ehci-to-h5-nanopi.patch"                # Nanopi Neo Plus 2
  patch -Np1 -i "${srcdir}/1003-drm-bridge-analogix_dp-Add-enable_psr-param.patch"                   # Pinebook Pro
  patch -Np1 -i "${srcdir}/1004-gpu-drm-add-new-display-resolution-2560x1440.patch"                  # Odroid
  patch -Np1 -i "${srcdir}/1005-panfrost-Silence-Panfrost-gem-shrinker-loggin.patch"                 # Panfrost
  patch -Np1 -i "${srcdir}/1006-arm64-dts-rockchip-Add-Firefly-Station-p1-support.patch"             # Firelfy Station P1
  patch -Np1 -i "${srcdir}/1007-drm-rockchip-add-support-for-modeline-32MHz-e.patch"                 # DP Alt Mode
  patch -Np1 -i "${srcdir}/1008-rk3399-rp64-pcie-Reimplement-rockchip-PCIe-bus-scan-delay.patch"     # RockPro64
  patch -Np1 -i "${srcdir}/1009-drm-meson-add-YUV422-output-support.patch"                           # Meson G12B
  patch -Np1 -i "${srcdir}/1010-arm64-dts-meson-add-initial-Beelink-GT1-Ultimate-dev.patch"          # Beelink
  patch -Np1 -i "${srcdir}/1011-add-dts-meson-g12b-ugoos-am6-plus.patch"                             # Meson Ugoos
  patch -Np1 -i "${srcdir}/1012-drm-panfrost-scheduler-improvements.patch"                           # Panfrost
  patch -Np1 -i "${srcdir}/1013-arm64-dts-rockchip-Add-PCIe-bus-scan-delay-to-RockPr.patch"          # RockPro64
  patch -Np1 -i "${srcdir}/1014-drm-rockchip-support-gamma-control-on-RK3399.patch"                  # RK3399 VOP
  patch -Np1 -i "${srcdir}/1015-media-rockchip-rga-do-proper-error-checking-in-probe.patch"          # Rockchip RGA
  #patch -Np1 -i "${srcdir}/1016-arm-dts-rockchip-firefly-station-m2.patch"                          # Firefly Station M2
  #patch -Np1 -i "${srcdir}/1017-add-dts-rk3568-station-p2.patch"                                    # Firefly Station P2
  #patch -Np1 -i "${srcdir}/1018-add-dts-rk3568-radxa-rock3a.patch"                                  # Radxa Rock 3A
  patch -Np1 -i "${srcdir}/1019-arm64-dts-rockchip-switch-to-hs200-on-rockpi4.patch"                 # Radxa Rock Pi 4
  patch -Np1 -i "${srcdir}/1020-arm64-dts-meson-remove-CPU-opps-below-1GHz-for-G12B-boards.patch"    # AMLogic [1/2]
  patch -Np1 -i "${srcdir}/1021-arm64-dts-meson-remove-CPU-opps-below-1GHz-for-SM1-boards.patch"     # AMLogic [2/2]
  patch -Np1 -i "${srcdir}/1022-arm64-dts-rockchip-Add-PCIe-bus-scan-delay-to-Rock-P.patch"          # Radxa Rock Pi 4

  # Assorted Pinebook, PinePhone and PineTab patches
  patch -Np1 -i "${srcdir}/2001-Bluetooth-Add-new-quirk-for-broken-local-ext-features.patch"         # Bluetooth
  patch -Np1 -i "${srcdir}/2002-Bluetooth-btrtl-add-support-for-the-RTL8723CS.patch"                 # Bluetooth
  patch -Np1 -i "${srcdir}/2003-arm64-allwinner-a64-enable-Bluetooth-On-Pinebook.patch"              # Bluetooth
  patch -Np1 -i "${srcdir}/2004-arm64-dts-allwinner-enable-bluetooth-pinetab-pinepho.patch"          # Bluetooth
  patch -Np1 -i "${srcdir}/2005-staging-add-rtl8723cs-driver.patch"                                  # Realtek WiFi
  patch -Np1 -i "${srcdir}/2006-arm64-dts-allwinner-pinetab-add-accelerometer.patch"                 # Accelerometer
  patch -Np1 -i "${srcdir}/2007-arm64-dts-allwinner-pinetab-enable-jack-detection.patch"             # Audio
  patch -Np1 -i "${srcdir}/2008-Bluetooth-Read-codec-capabilities-only-if-supported.patch"           # Bluetooth
  patch -Np1 -i "${srcdir}/2009-btsdio-Do-not-bind-to-non-removable-BCM4345-and-BCM43455.patch"      # Bluetooth
  patch -Np1 -i "${srcdir}/2010-brcmfmac-USB-probing-provides-no-board-type.patch"                   # Bluetooth
  patch -Np1 -i "${srcdir}/2011-dts-rockchip-Adapt-and-adopt-Type-C-support-from-Pin.patch"          # DP Alt Mode

  # Pinebook Pro Type-C patches from megous; original patch numbers found
  # on https://xff.cz/kernels/5.16/patches/ are retained, with just the first
  # digit changed from 0 to 3, to make tracking easier
  patch -Np1 -i "${srcdir}/3172-arm64-dts-rk3399-pinebook-pro-Fix-USB-PD-charging.patch"
  patch -Np1 -i "${srcdir}/3174-arm64-dts-rk3399-pinebook-pro-Improve-Type-C-support.patch"
  patch -Np1 -i "${srcdir}/3176-arm64-dts-rk3399-pinebook-pro-Remove-redundant-pinct.patch"
  patch -Np1 -i "${srcdir}/3376-drm-rockchip-cdn-dp-Disable-CDN-DP-on-disconnect.patch"
  patch -Np1 -i "${srcdir}/3392-usb-typec-fusb302-Set-the-current-before-enabling-pu.patch"
  patch -Np1 -i "${srcdir}/3396-usb-typec-fusb302-Update-VBUS-state-even-if-VBUS-int.patch"
  patch -Np1 -i "${srcdir}/3398-usb-typec-fusb302-Add-OF-extcon-support.patch"
  patch -Np1 -i "${srcdir}/3399-usb-typec-fusb302-Fix-register-definitions.patch"
  patch -Np1 -i "${srcdir}/3400-usb-typec-fusb302-Clear-interrupts-before-we-start-t.patch"
  patch -Np1 -i "${srcdir}/3401-usb-typec-typec-extcon-Add-typec-extcon-bridge-drive.patch"
  patch -Np1 -i "${srcdir}/3402-phy-rockchip-typec-Make-sure-the-plug-orientation-is.patch"
  patch -Np1 -i "${srcdir}/3457-phy-rockchip-inno-usb2-More-robust-charger-detection.patch"
  patch -Np1 -i "${srcdir}/3458-usb-typec-extcon-Don-t-touch-charger-proprties.patch"
  patch -Np1 -i "${srcdir}/3459-arm64-dts-rk3399-pinebook-pro-Don-t-allow-usb2-phy-d.patch"

  cat "${srcdir}/config" > ./.config

  # Add pkgrel to extraversion
  sed -ri "s|^(EXTRAVERSION =)(.*)|\1 \2-${pkgrel}|" Makefile

  # Don't run depmod on "make install", we'll do that ourselves in packaging
  sed -i '2iexit 0' scripts/depmod.sh
}

build() {
  cd ${_srcname}

  # get kernel version
  make prepare

  # load configuration
  # Configure the kernel. Replace the line below with one of your choice.
  #make menuconfig # CLI menu for configuration
  #make nconfig # new CLI menu for configuration
  #make xconfig # X-based configuration
  #make oldconfig # using old config from previous kernel version
  # ... or manually edit .config

  # Copy back our configuration (use with new kernel version)
  #cp ./.config /var/tmp/${pkgbase}.config

  ####################
  # stop here
  # this is useful to configure the kernel
  #msg "Stopping build"
  #return 1
  ####################

  #yes "" | make config

  # build!
  unset LDFLAGS
  make ${MAKEFLAGS} Image modules
  # Generate device tree blobs with symbols to support applying device tree overlays in U-Boot
  make ${MAKEFLAGS} DTC_FLAGS="-@" dtbs
}

_package() {
  pkgdesc="The Linux Kernel and modules - ${_desc}"
  depends=('coreutils' 'linux-firmware' 'kmod' 'initramfs')
  optdepends=('crda: to set the correct wireless channels of your country')
  provides=('kernel26' "linux=${pkgver}")
  conflicts=('kernel26' 'linux')
  replaces=('linux-armv8' 'linux-aarch64')
  backup=("etc/mkinitcpio.d/${pkgbase}.preset")
  install=${pkgname}.install

  cd ${_srcname}

  KARCH=arm64

  # get kernel version
  _kernver="$(make kernelrelease)"
  _basekernel=${_kernver%%-*}
  _basekernel=${_basekernel%.*}

  mkdir -p "${pkgdir}"/{boot,usr/lib/modules}
  make INSTALL_MOD_PATH="${pkgdir}/usr" modules_install
  make INSTALL_DTBS_PATH="${pkgdir}/boot/dtbs" dtbs_install
  cp arch/$KARCH/boot/Image "${pkgdir}/boot"

  # make room for external modules
  local _extramodules="extramodules-${_basekernel}${_kernelname}"
  ln -s "../${_extramodules}" "${pkgdir}/usr/lib/modules/${_kernver}/extramodules"

  # add real version for building modules and running depmod from hook
  echo "${_kernver}" |
    install -Dm644 /dev/stdin "${pkgdir}/usr/lib/modules/${_extramodules}/version"

  # remove build and source links
  rm "${pkgdir}"/usr/lib/modules/${_kernver}/{source,build}

  # now we call depmod...
  depmod -b "${pkgdir}/usr" -F System.map "${_kernver}"


  # sed expression for following substitutions
  local _subst="
    s|%PKGBASE%|${pkgbase}|g
    s|%KERNVER%|${_kernver}|g
    s|%EXTRAMODULES%|${_extramodules}|g
  "

  # install mkinitcpio preset file
  sed "${_subst}" ../linux.preset |
    install -Dm644 /dev/stdin "${pkgdir}/etc/mkinitcpio.d/${pkgbase}.preset"

  # install pacman hooks
  sed "${_subst}" ../60-linux.hook |
    install -Dm644 /dev/stdin "${pkgdir}/usr/share/libalpm/hooks/60-${pkgbase}.hook"
  sed "${_subst}" ../90-linux.hook |
    install -Dm644 /dev/stdin "${pkgdir}/usr/share/libalpm/hooks/90-${pkgbase}.hook"
}

_package-headers() {
  pkgdesc="Header files and scripts for building modules for linux kernel - ${_desc}"
  provides=("linux-headers=${pkgver}")
  conflicts=('linux-headers')
  replaces=('linux-aarch64-headers')

  cd ${_srcname}
  local _builddir="${pkgdir}/usr/lib/modules/${_kernver}/build"

  install -Dt "${_builddir}" -m644 Makefile .config Module.symvers
  install -Dt "${_builddir}/kernel" -m644 kernel/Makefile

  mkdir "${_builddir}/.tmp_versions"

  cp -t "${_builddir}" -a include scripts

  install -Dt "${_builddir}/arch/${KARCH}" -m644 arch/${KARCH}/Makefile
  install -Dt "${_builddir}/arch/${KARCH}/kernel" -m644 arch/${KARCH}/kernel/asm-offsets.s
  install -Dt "${_builddir}" -m644 vmlinux 

  cp -t "${_builddir}/arch/${KARCH}" -a arch/${KARCH}/include
  mkdir -p "${_builddir}/arch/arm"
  cp -t "${_builddir}/arch/arm" -a arch/arm/include

  install -Dt "${_builddir}/drivers/md" -m644 drivers/md/*.h
  install -Dt "${_builddir}/net/mac80211" -m644 net/mac80211/*.h

  # http://bugs.archlinux.org/task/13146
  install -Dt "${_builddir}/drivers/media/i2c" -m644 drivers/media/i2c/msp3400-driver.h

  # http://bugs.archlinux.org/task/20402
  install -Dt "${_builddir}/drivers/media/usb/dvb-usb" -m644 drivers/media/usb/dvb-usb/*.h
  install -Dt "${_builddir}/drivers/media/dvb-frontends" -m644 drivers/media/dvb-frontends/*.h
  install -Dt "${_builddir}/drivers/media/tuners" -m644 drivers/media/tuners/*.h

  # add xfs and shmem for aufs building
  mkdir -p "${_builddir}"/{fs/xfs,mm}

  # copy in Kconfig files
  find . -name Kconfig\* -exec install -Dm644 {} "${_builddir}/{}" \;

  # remove unneeded architectures
  local _arch
  for _arch in "${_builddir}"/arch/*/; do
    [[ ${_arch} == */${KARCH}/ || ${_arch} == */arm/ ]] && continue
    rm -r "${_arch}"
  done

  # remove documentation files
  rm -r "${_builddir}/Documentation"

  # remove now broken symlinks
  find -L "${_builddir}" -type l -printf 'Removing %P\n' -delete

  # strip scripts directory
  local file
  while read -rd '' file; do
    case "$(file -bi "$file")" in
      application/x-sharedlib\;*)      # Libraries (.so)
        strip $STRIP_SHARED "$file" ;;
      application/x-archive\;*)        # Libraries (.a)
        strip $STRIP_STATIC "$file" ;;
      application/x-executable\;*)     # Binaries
        strip $STRIP_BINARIES "$file" ;;
      application/x-pie-executable\;*) # Relocatable binaries
        strip $STRIP_SHARED "$file" ;;
    esac
  done < <(find "${_builddir}" -type f -perm -u+x ! -name vmlinux -print0 2>/dev/null)
  strip $STRIP_STATIC "${_builddir}/vmlinux"
  
  # remove unwanted files
  find ${_builddir} -name '*.orig' -delete
}

pkgname=("${pkgbase}" "${pkgbase}-headers")
for _p in ${pkgname[@]}; do
  eval "package_${_p}() {
    _package${_p#${pkgbase}}
  }"
done
