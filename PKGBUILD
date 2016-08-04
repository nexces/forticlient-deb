# Maintainer: Adrian Piotrowicz <nexces+chakraos@nxstudio.pl>

pkgname=forticlient-deb
pkgver=4.4.2329
pkgrel=1
pkgdesc="FortiClient SSL VPN from hadler.me packages"
arch=(x86_64)
url="https://hadler.me/linux/forticlient-sslvpn-deb-packages/"
license=('MIT')
depends=()
makedepends=('binutils')
provides=('forticlient')
conflicts=('forticlient')
replaces=('forticlient')
options=(!strip staticlibs)
source=(https://hadler.me/files/forticlient-sslvpn_${pkgver}-${pkgrel}_amd64.deb)
sha256sums=('d2f7a22f0e21fa11fda3a3609eac3582979b4348141120a6d8599a8ac9480dda')

prepare() {
	cd "$srcdir"
	ar p forticlient-sslvpn_${pkgver}-${pkgrel}_amd64.deb control.tar.gz | tar xzf -
	ar p forticlient-sslvpn_${pkgver}-${pkgrel}_amd64.deb data.tar.xz | tar xJf -
}

check() {
	cd "$srcdir"
	md5sum -c md5sums || return 1
}

package() {
	cd "$srcdir"
	mv opt "$pkgdir/"
	mv usr "$pkgdir/"
}
