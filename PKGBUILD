pkgname=bootsplash
pkgver=0.1
pkgrel=2
pkgdesc='Bootsplash'
arch=('i686' 'x86_64' 'aarch64')
license=('GPL2')
makedepends=('gcc' 'imagemagick')
options=('!libtool' '!emptydirs')
source=('https://gitlab.manjaro.org/manjaro-arm/packages/extra/bootsplash-packer/-/raw/master/bootsplash_file.h'
        'https://gitlab.manjaro.org/manjaro-arm/packages/extra/bootsplash-packer/-/raw/master/bootsplash-packer.c'
        'bootsplash.sh'
        'bootsplash.initcpio_install'
        'spinner.gif'
        'logo.png')
md5sums=('4a251bae57a652bfa32361144815153c'
         '44df81a35ef9d008fffdc94800694f9c'
         '7eed6221f5fb41d07a10581e0987e0ae'
         '4dcf4ae407080cb7014cff4f5f9baac9'
         '6267db671e80e80a0a6db81126a2d9dd'
         'ff61bd3f636a2be51c912ea30491a05a')

build() {
    cd "${srcdir}"
	  ${CC:-gcc} $CFLAGS -o bootsplash-packer bootsplash-packer.c
    sh ./bootsplash.sh
}

package() {
  cd "${srcdir}"
  install -Dm644 bootsplash "$pkgdir/usr/lib/firmware/bootsplash"
  install -Dm644 bootsplash.initcpio_install "$pkgdir/usr/lib/initcpio/install/bootsplash"
}
