# Maintainer: Daniel Beecham <daniel@lunix.se>
# Contributor: Jens Staal <staal1978@gmail.com>

options=(!strip)
pkgname="base2busybox-xz"
pkgver="1"
pkgrel=2
pkgdesc="Replaces base xz with corresponding commands from Busybox."
arch=('any')
url="http://busybox.net/"
license=('GPLv2')
depends=('busybox')
provides=('xz=5.0.3-1')
conflicts=('xz')
source=('missing')
md5sums=('afbbedb17e5e96ed6047e840249b1bc0')

_missing=($srcdir/missing)

build() {
    msg "creating package directories"
    mkdir "$pkgdir/usr"
    mkdir "$pkgdir/usr/bin"

    msg "creating symlinks for /usr/bin"
    cd $pkgdir/usr/bin
    ln -s /bin/busybox lzcat
    ln -s /bin/busybox lzma
    ln -s /bin/busybox unzlma
    ln -s /bin/busybox xzcat
    ln -s /bin/busybox xz
    ln -s /bin/busybox unxz

    warning "This package is missing binaries from the xz package which might be important."
    warning "Here is a list of missing binaries:"
    warning "$(cat $_missing)"
}
 
