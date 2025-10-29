pkgname=flarebird-install-scripts
pkgver=31
pkgrel=3
pkgdesc="Scripts to aid in installing Flarebird Linux"
arch=('x86_64')
url="https://gitlab.archlinux.org/archlinux/arch-install-scripts"
license=('GPL-2.0-only')
depends=(
    'gawk'
    'bash'
    'coreutils'
    'git'
    'grep'
    'pacman'
    'rsync'
    'util-linux'
)
makedepends=('python-asciidoc')
source=(git+https://gitlab.archlinux.org/archlinux/arch-install-scripts#tag=v${pkgver}
    flarebird-install-scripts.patch)
sha256sums=(77b4f4eb96ecb6031e3ed0ff4c68de1fbeb28deae9615cfe91e2632c1fe629e2
    93cf335c8f88d1048caa7980f31e1f17666ae28c7aac1778ec1853479271e572)

prepare() {
    cd arch-install-scripts

    git apply -3 ${srcdir}/flarebird-install-scripts.patch
}

build() {
    cd arch-install-scripts

    make CC="${CHOST}-gcc"
}

package() {
    cd arch-install-scripts

    make DESTDIR=${pkgdir} PREFIX=/usr  install
}
