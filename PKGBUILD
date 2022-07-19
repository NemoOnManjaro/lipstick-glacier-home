## $Id$
# Contributor: Bart Ribbers <bribbers@disroot.org>
# Contributor: Alexey Andreyev <aa13q@ya.ru>
# Contributor: Chipligin Sergey (NeoChapay) <neochapay@gmail.com>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>

pkgname=lipstick-glacier-home-git
_host="github.com"
_project=nemomobile-ux
_branch=master
pkgver=0.37.6
pkgrel=1
pkgdesc="A nice homescreen for Glacier experience"
arch=('x86_64' 'aarch64')
url="https://$_host/$_project/glacier-home"
license=('BSD-3-Clause AND MIT')
depends=('bluez-qt'
	'qt5-graphicaleffects'
	'qt5-multimedia'
	'qt5-feedback'
	'qtmpris'
	'qt5-lipstick'
	'qt5-quickcontrols-nemo'
	'nemo-qml-plugin-configuration'
	'nemo-qml-plugin-statusnotifier'
	'nemo-qml-plugin-time'
	'nemo-qml-plugin-contacts'
	'nemo-qml-plugin-notifications'
	'nemo-qml-plugin-connectivity'
	'glacier-settings'
	'geoclue1'
	'mlite'
	'qt-mobility-haptics-ffmemless'
	'ngfd'
	'pulseaudio-module-keepalive')

makedepends=(	'extra-cmake-modules'
	'qt5-wayland'
	'qt5-tools'
	'nemo-qml-plugin-devicelock'
	'bluez-qt'
	'polkit-qt5'
	'mce-headers>=1.30.0')
optdepends=()
source=("${url}/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('d9a5a07bf54ae4988ff16d034aba9ae656dfc1629d1b099b71084934f8136901')

prepare() {
    cd "${srcdir}/${pkgname}"
}

build() {
  cd "${srcdir}/${pkgname}"
  cmake -B build \
        -DCMAKE_BUILD_TYPE=None \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_INSTALL_LIBDIR=lib \
        -DCMAKE_INSTALL_SYSCONFDIR=/etc \
        -DUSE_GEOCLUE2=false
  make -C build
}

package() {
  cd "${srcdir}/${pkgname}"
  DESTDIR="$pkgdir" make -C build install
}
