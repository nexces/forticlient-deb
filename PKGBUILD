# Maintainer: Adrian Piotrowicz <nexces+chakraos@nxstudio.pl>

pkgname=forticlient-deb
pkgver=4.4.2330
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
sha256sums=('ebeec66baf5d15c40eaf1b9f4c721b29252d6314a354e5798ca6a036279e8640')

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
