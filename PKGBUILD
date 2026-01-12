# Maintainer: csmantle <aur at csmantle dot top>
# shellcheck shell=bash
# shellcheck disable=SC2034,SC2154,SC2164

_pkgname=loonggpu-kernel-dkms
pkgname="${_pkgname}-bin"
_modulever='1.0.2'
_origver="${_modulever}-lnd25.1~rc1.7"
_pkgver="$(printf '%s' "$_origver" | tr -- '-~' '_.')"
pkgver="$_pkgver"
pkgrel=2
pkgdesc='Kernel module sources (DKMS) for LoongGPU kernel-mode drivers'
arch=('loong64')
url='https://pkg.loongnix.cn/'
license=('LicenseRef-Proprietary')
depends=('dkms')
makedepends=('patch')
provides=()
conflicts=()

_debname="${_pkgname}_${_origver}_loong64.deb"
source=(
  "${_debname}::https://pkg.loongnix.cn/loongnix/25/pool/non-free/l/loonggpu-graphics-drivers/${_debname}"
  '0001-loonggpu-fix-build-without-CONFIG_MMU_NOTIFIER.patch'
  '0002-AOSCOS-loonggpu-remove-driver-date.patch'
  '0003-AOSCOS-loonggpu-Use-ccflags-y-instead-of-EXTRA_CFLAG.patch'
  '0004-loonggpu-Remove-unused-fbdev_list-field-in-gsgpu_fra.patch'
  '0005-loonggpu-Remove-the-unused-loonggpu_fbdev_total_size.patch'
  '0006-loonggpu-Improve-fbdev-object-test-helper.patch'
  '0007-loonggpu-Remove-struct-gsgpu_fbdev-and-add-some-clea.patch'
  '0008-loonggpu-Move-fbdev-cleanup-code-into-fb_destroy-cal.patch'
  '0009-loonggpu-Remove-load-callback-from-kms_driver.patch'
  '0010-AOSCOS-loonggpu-Adapt-for-drm_sched_init-struct-para.patch'
  '0011-AOSCOS-loonggpu-Adapt-for-renaming-of-from_timer-to-.patch'
  '0012-AOSCOS-loonggpu-Adapt-for-renaming-of-del_timer_sync.patch'
  '0013-loonggpu-Remove-redundant-info-par-assignment.patch'
  '0014-loonggpu-Remove-test-for-screen_base-in-fbdev-probin.patch'
  '0015-loonggpu-Correctly-clean-up-failed-display-probing.patch'
  '0016-loonggpu-Implement-client-based-fbdev-emulation.patch'
  '0017-loonggpu-Remove-a-redundant-gsgpu_fbdev_client_hotpl.patch'
  '0018-loonggpu-Disable-outputs-when-releasing-fbdev-client.patch'
  '0019-loonggpu-Run-DRM-default-client-setup.patch'
  '0020-loonggpu-bridge-make-is_resolution_valid-static.patch'
  '0021-loonggpu-bridge-constify-struct-drm_display_mode-poi.patch'
  '0022-loonggpu-bridge-Adapt-for-recent-kernel-API-changes.patch'
  '0023-loonggpu-Remove-the-check-against-moving-pinned-BOs.patch'
  '0024-loonggpu-Remove-dead-code.patch'
  '0025-loonggpu-NFC-Clean-up-gsgpu_bo_move.patch'
  '0026-loonggpu-Handle-tt-moves-properly.patch'
  '0027-loonggpu-Use-multihop.patch'
  '0028-loonggpu-Drop-the-unused-no_wait_gpu-parameter-of-gs.patch'
  '0029-loonggpu-Drop-lg_ttm_tt_bind.patch'
  '0030-loonggpu-Remove-an-invalid-const-qualifier.patch'
  '0031-loonggpu-Fix-the-parameter-order-of-a-kmalloc_array-.patch'
  '0032-loonggpu-Pass-DRM-client-ID-to-drm_sched_job_init.patch'
  '0033-loonggpu-Adapt-for-drm_get_format_info-API-change.patch'
  '0034-loonggpu-Adapt-for-.fb_create-API-change.patch'
  '0035-loonggpu-Adapt-for-drm_helper_mode_fill_fb_struct-AP.patch'
  '0036-loonggpu-Pass-along-the-format-info-from-.fb_create-.patch'
  '0037-loonggpu-Adapt-for-the-rename-of-DRM_GPU_SCHED_STAT_.patch'
  '0038-loonggpu-Don-t-directly-use-ttm_bo_get.patch'
  '0039-loonggpu-Get-rid-of-drm_sched_job.id.patch'
  '0040-loonggpu-bridge-alloc-bridge-phy-using-devm_drm_brid.patch'
  '0041-loonggpu-Get-rid-of-ida_simple_get-and-ida_simple_re.patch'
  '0042-loonggpu-drop-LG_ZONE_MANAGED_PAGES.patch'
  '0043-loonggpu-ensure-clearing-the-mapping-field-of-ttm-pa.patch'
  '0044-loonggpu-Handle-the-different-drm_client_setup.h-loc.patch'
  '0045-loonggpu-Handle-the-error-from-gsgpu_driver_load_kms.patch'
  '0046-loonggpu-fix-typo-mistake-in-include-gsgpu_ttm_resou.patch'
  '0047-loonggpu-add-cflag-std-gnu11-to-conftest-as-gcc-15-s.patch'
  '0048-loonggpu-Drop-CLEAN-from-dkms.conf.patch'
  '0049-loonggpu-bridge-remove-calls-to-drm_do_get_edid.patch'
  '0050-loonggpu-don-t-return-an-error-if-backlight-initiali.patch'
  '0051-loonggpu-backlight-get-PWM-correctly-and-skip-GPIO-f.patch'
  '0052-loonggpu-Only-build-a-dummy-if-page-size-is-4-KiB.patch'
  '0053-bridge_phy-add-conditional-compilation-for-linux-6.1.patch'
  '0054-loonggpu-bridge-remove-redundant-bridge-func-vptr-as.patch'
  '0055-loonggpu-bridge-make-bridge_phy_alloc-return-ERR_PTR.patch'
  '0056-loonggpu-bridge-make-some-functions-static.patch'
  '0057-loonggpu-adapt-for-ttm_device_init-API-change.patch'
  '0058-loonggpu-conftest-add-fms-extensions-to-CFLAGS.patch'
  '0059-loonggpu-Drop-the-call-to-drm_fb_helper_alloc_info.patch'
  '0060-loonggpu-use-ttm_resource_manager_cleanup-instead-of.patch'
  '0061-loonggpu-handle-the-rename-of-ttm_bo_put-to-ttm_bo_f.patch'
  '0062-loonggpu-remove-gsgpu_driver_lastclose_kms-on-Linux-.patch'
  '0063-loonggpu-handle-the-pci_resize_resource-API-change-i.patch'
)
sha256sums=('c2c2969e0852ff728c9c177a83112578ad8e8428ee12e24d5d85c143acdc143d'
            'd872dc59c916fcc0e492d0b7beef56d741c96c70d5f43d47ee5ed69fe8a3f062'
            '7aac8db5508c9345a3329731299d5f065a867a028a00211cd8cd1256189be9c3'
            'e25a8e63c4e6549bb47371490344e622f461bd7300702480463b74880b3e6ef2'
            'a039a33d7d14664beb2ec7ec099e25073c5b23fd52046d1b175dafcc717e3ca1'
            '60501ed18c34a9234a8218cdacdce434cf158eb702710ebdf4ec86cdf00090ce'
            'a44b422b22d2d709905b8f8ac88774a67be70bb46f837477afc5be9909da1241'
            'a74a3a51c1b405a9df4750491d076280806f83801ca956d500f72f79ae0b8b4c'
            '68ee5f9fc43b0f4821e8584e211a5d31881772a6b38ca7be7820133c8d079d2d'
            'd322ed2cab7a0c0bd1e8f759cb7682f5826e71114078151fb4cbdd8849224ad3'
            '2ed15e99025485063c5c8ecd0ec20e475d5843e5d8f2118e265f1c2b7f10dc7e'
            'e041e04b73c9fdba4345e95f10455b0a7b041541c2fc4a842231f7ac41bbb9f0'
            '7222d6b707869f6da551cedda2f059ff05020d024b0bb88d319888fecc559a6b'
            'ae95cc581cd92a3f95a0af2756915d2a6bca16f242cf619756a5fc97023ab30d'
            '12ca57cc439f2b2892cb6f4bcfe57dcfde802da878532dcc7f04712a409ea12b'
            'cfca60c34a2e4fb4c72793f809ddd62db55a73aa7e39f22851d1566017bc3d86'
            '93c9cdc0f7d0d632ce2c0666bcb9cf740105be0261f8084af89051987ecea20c'
            'a247b76f8e1e3a34b7eaab4227cd5497c6ba4f7c6fc764b6a81b6f5e0c0b1f30'
            '908d49110ef076b3557f4447209dde427d8e8008121d9d5736b5dddc2623f9e5'
            'c29eae1dfada7186707856076df96972aa8d519504687327d89cc1249222e9c4'
            '58de2f3f3e0549d67bdbc77293825cc2809ae5a3f76ce2da884cc6f613a08dfa'
            '363a79e8389bbaefac0622cde29c62235b2a23ca4415510eff571f68624ec685'
            '44b16d03060a636d45a9bd84a8a44f0115d0eadfdaa8aea2204b689e24239447'
            '36dc1adf02bc22702b76a662909fa1476aea88fac50a407b77f3748ddd944677'
            '18ff02b38d4f3240545f5a9618d89f2037e380cf20819ef333d9c6daebc90483'
            'd1df3ac02e94224c0be269744a46e4560e6fae1e2290f706eacbcf9f2114473c'
            '0ea11a5a6db22555252c10adf7d03cd96c53b335c14388bc9a577f39082d6437'
            '837dc6aa926433859a0acb1eb7d9a0df22d727c2db0571105dc57033bef18426'
            '0f5b196c412a30b627d8a6d31b13e88fb2df4b91d656f7c0840f2e95cab627bf'
            '5827d02a0abe5b7d39050553b8c70fb2b95fa8564dfcf58a87e63ec27642af9e'
            'a91ebff1b86c06ba7e73fc27f8f24d17feb593cad242f85230f7e8d5df8f482e'
            'aee8779a08983ba5d5ffea8b563071522f595f1a0aee7b03f76c20760d2f1041'
            '4b63d18ff9e699b3860203dafe8aa6ba1eab21993421a77f60b7bf139d1c605f'
            '5958fa5e6041c3740822fcc945ff2c2504a6fa70ccc78a961a4722f8543c697f'
            '1625fcd317eb6eb083c4eb4451ff3ef8ad09594ecc090158115d7db9fc3dfb9c'
            '84a3e2c22631c483b2153110a201dd7e842c308c3daedc3a4fb1e5e30425e883'
            'ada6912ab62ab39307dda99d7c2779c134dab8aa8fd4722edaced4a633d00d62'
            'f7b6a7b0cd6ec899799e045638f51f4acd8be6f35e2b55b627854754da6fcfa1'
            '6af26fbb958ac42a914f3648788dc7ebfb8936ac341080a17ddc7bed70448d69'
            '8935cf5dc13dae1f101fce424aa71ce65aa12d4b38b2d914ac4acbf7542adfc7'
            '47d0dd6c635b028b2bb20a1fefeb64dc294ec61821cf6ef65de1625233039a68'
            '5808e2a9a811a1d0edd6d9769afa24f8e9062a901497ff855bfebaf6445e75e1'
            '3e9bb059198f31ff6c2938e8e9f73866f397a80df1cae1f0b79fb0fe8efbbc39'
            'b01623effb3cd8f46a5251f308f57302d4d0175b44b61d08ad6fcde1e883baa3'
            '008e92eb9b5edc4ca56ca8ef00ac526dad583f15e8728460782912c6f39ab1cb'
            'dd123d39d3538f2639c8dea3fad9cebe90614fc684e8c643a60159f4ef579fc5'
            'd5c4939eedcec600a5f8f939fc10d45696fe4a03d626cc276393d11ea513a100'
            '59843692955a2534edaf53677319612fdd18fbcc7ca3aa96dfd122a043fcf06c'
            '16f25270eb719c8daae1237a31bab093151148a1700decd0b93e97cb63ed6a08'
            '2ca302da81d8e555ed6566614752810463af7cdbab468b47ecb6f24d0f5c513e'
            '01123e25bf355ac0bb47f576a21474ffb34546b0c9e30cf451e4b01b98967e7c'
            '2b33e52280a871eb47b3ae27bd20d2a900c182d6a8fdb4c1baa0bdde8618abfc'
            'd06b87c128d1c495101fcd9cf90cf5c0f396c0dc70e1468d6ea63761d1197339'
            '207c677b3cafda1624665e5f9a28590ac9f6d7f87114bc9edb5296540af6f1d4'
            'b65b4b6a782ff8e08b472eb7d0a37d7ba8426ce589595c0ba2b7c96c29b7b809'
            '5206b274e39e4c397f24c066bbf540669c633625cf71f28e3dc6ebe0c3bd8077'
            'a0c49ae70f936a2017caa11d4b9ca7b025551daaaf2cbe49b338663159c6dd74'
            '2b5dd4b716d98376b29f4d9c2b800b1877455b32670b798d7aebf6986e5173d5'
            '505b1a1a8d61e9b4772af313ae6666ac23ddea431f16e0d8f4e192c2cbf8cc9a'
            'b5d76494ef9d87eb2309c34ceef40f1b55be4ec2c83adee28f800d60e4748665'
            '8c43d610ed0a7a9ae9c49aba52a0777a321635d85523a0f5c679087fe995c9f6'
            '2c732d5a38ec052f426530c00e6a105703573a2dc10e276533bd4c155661cf7e'
            'fc6c306c672a43ccd1ab23e213e2218a8782bb82062099f1e3007d8423825262'
            '01d40ff262f29de6db40095485146d5f40ea187df60f1f382e66342eeea2d469')

prepare() {
  cd "$srcdir"

  rm -rfv debroot
  mkdir -p debroot

  echo 'Extracting .deb archive...'
  bsdtar -xvf "$_debname" -C "$srcdir"
  tar -xvf data.tar.* -C "$srcdir"/debroot

  cd "$srcdir"/debroot/usr/src/loonggpu-"$_modulever"
  for patch_file in "$srcdir"/*.patch; do
    patch -Np1 -i "$patch_file"
  done
}

package() {
  cd "$srcdir"/debroot
  cp -va --no-preserve=ownership . "$pkgdir"/
}

