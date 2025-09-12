pkgname=flarebird-install-scripts
pkgver=29
pkgrel=2
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
    0e6f728910eab20043b6a92912030e464668c180a8230bcbe2424995fc7602e9)

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
