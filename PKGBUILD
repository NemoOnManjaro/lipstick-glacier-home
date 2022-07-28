## $Id$
# Contributor: Bart Ribbers <bribbers@disroot.org>
# Contributor: Alexey Andreyev <aa13q@ya.ru>
# Contributor: Chipligin Sergey (NeoChapay) <neochapay@gmail.com>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>

pkgname=lipstick-glacier-home
_host="github.com"
_project=nemomobile-ux
_branch=master
pkgver=0.37.7
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
	'glacier-settings>=0.6'
	'geoclue1'
	'mlite'
	'qt-mobility-haptics-ffmemless'
	'ngfd'
	'nemo-qml-plugin-devicelock'
	'bluez-qt'
	'qt5-wayland'
	'qt5-tools'
	'polkit-qt5'
	'pulseaudio-module-keepalive')

makedepends=('extra-cmake-modules'
	'mce-headers>=1.30.0')
optdepends=()
source=("${url}/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('3b137a5b35a99b62a0d2ec5623c64aa220674e1065f564b8deceeb019e453b7d')

build() {
  cd glacier-home-$pkgver
  cmake -B build \
        -DCMAKE_BUILD_TYPE=None \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_INSTALL_LIBDIR=lib \
        -DCMAKE_INSTALL_SYSCONFDIR=/etc \
        -DUSE_GEOCLUE2=false
  make -C build
}

package() {
  cd glacier-home-$pkgver
  DESTDIR="$pkgdir" make -C build install
}
