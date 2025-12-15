# Maintainer: George Hu <integral@archlinux.org>
# Contributor: Maxime Gauduin <alucryd@archlinux.org>
# Contributor: Tofe <chris.chapuis@gmail.com>
# Contributor: erm67 <erm67@yahoo.it>

pkgname=cairo-dock
pkgver=3.6.1.1
pkgrel=1
pkgdesc="Light eye-candy fully themable animated dock"
arch=('x86_64')
url="https://github.com/n3ptune-plan3t/${pkgname}-core"
license=('GPL-3.0-or-later')
depends=(
	'gtk3'
	'gdk-pixbuf2'
	'glib2'
	'cairo'
	'pango'
	'librsvg'
	'dbus'
	'dbus-glib'
	'libxml2'
	'libxrender'
	'glu'
	'curl'
	'libx11'
	'libxtst'
	'libxcomposite'
	'libxrandr'
	'libxinerama'
	'wayland'
	'json-c'
	'gtk-layer-shell'
)
makedepends=('cmake' 'extra-cmake-modules' 'wayland-protocols')
optdepends=('cairo-dock-plug-ins: Plugins for Cairo-Dock')
source=("${pkgname}-${pkgver}.tar.gz::${url}/archive/${pkgver}.tar.gz")
sha256sums=('a16083625b26cf32b02a630454b2e6ec5e032e55e72ddcf98bd99461b86abb2a')

build() {
	cmake -B build \
		-S "${pkgname}-core-${pkgver}" \
		-D CMAKE_BUILD_TYPE=None \
		-D CMAKE_INSTALL_PREFIX=/usr \
		-D enable-desktop-manager=True \
		-D enable-systemd-service=True

	cmake --build build
}

package() {
	DESTDIR="${pkgdir}" cmake --install build
}
