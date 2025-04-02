## $Id$
# Contributor: Bart Ribbers <bribbers@disroot.org>
# Contributor: Alexey Andreyev <aa13q@ya.ru>
# Contributor: Chipligin Sergey (NeoChapay) <neochapay@gmail.com>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>

pkgname=lipstick-glacier-home
_host="github.com"
_project=nemomobile-ux
_branch=master
pkgver=1.1.2
pkgrel=1
pkgdesc="A nice homescreen for Glacier experience"
arch=('x86_64' 'aarch64')
url="https://$_host/$_project/glacier-home"
license=('BSD-3-Clause AND MIT')
depends=('qt6-multimedia'
	'qt6-feedback'
	'amber-mpris'
	'qt6-lipstick'
	'qt6-quickcontrols-nemo>=6.0.0'
	'nemo-qml-plugin-configuration>=0.2.8'
	'nemo-qml-plugin-statusnotifier'
	'nemo-qml-plugin-time>=0.1.7'
	'nemo-qml-plugin-notifications>=1.2.25'
	'nemo-qml-plugin-connectivity>=0.2.15'
	'glacier-settings>=0.8'
	'geoclue1'
	'mlite6'
	'qt-mobility-haptics-ffmemless>=0.2.9'
	'ngfd'
	'nemo-qml-plugin-devicelock'
	'bluez-qt>=6.0'
	'qt6-wayland'
	'polkit-qt6'
	'pulseaudio-module-keepalive'
	'glacier-settings-developermode')

makedepends=('extra-cmake-modules>=6.0'
	'mce-headers>=1.30.0'
	'qt6-tools')
optdepends=()
source=("${url}/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('79037483018d8274f13bd3b3d16d396d2ebd0438689aa9c5a80d03e10e888e42')

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
