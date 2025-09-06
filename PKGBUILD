pkgname=flarebird-install-scripts
pkgver=29
pkgrel=1
pkgdesc="Scripts to aid in installing Flarebird Linux"
arch=('x86_64')
url="https://gitlab.archlinux.org/archlinux/arch-install-scripts"
license=('GPL-2.0-only')
depends=(
    'gawk'
    'bash'
    'coreutils'
    'grep'
    'pacman'
    'util-linux'
)
makedepends=('python-asciidoc')
source=(https://gitlab.archlinux.org/archlinux/arch-install-scripts/-/archive/v${pkgver}/arch-install-scripts-v${pkgver}.tar.gz
    flarebird-install-scripts.patch)
sha256sums=(9b39bcb93e0e104e14d3cfa60a094d35e76d39276af3aeac69620a89f71abfc7
    ee4c5e0e0d1b9f4b997f324c0dd1a9950747de40454bc88e540b31cf6267294d)

prepare() {
    cd arch-install-scripts-v${pkgver}

    patch -Np1 -i ${srcdir}/flarebird-install-scripts.patch
}

build() {
    cd arch-install-scripts-v${pkgver}

    make CC="${CHOST}-gcc"
}

package() {
    cd arch-install-scripts-v${pkgver}

    make DESTDIR=${pkgdir} PREFIX=/usr  install
}
