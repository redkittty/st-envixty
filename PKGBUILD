# Maintainer: Envixty (redkittty on Github) <redkitttyemails@gmail.com>
pkgname=st-envixty-git # '-bzr', '-git', '-hg' or '-svn'
pkgver=0.0.1
pkgrel=1
pkgdesc="Envixty's personal ST Configuration"
arch=(x86_64)
url="https://github.com/redkittty/st-envixty.git"
license=('MIT')
groups=()
depends=()
makedepends=('git')
provides=(st)
conflicts=(st)
replaces=()
backup=()
options=()
source=("git+$url")
noextract=()
sha256sums=('SKIP')


pkgver() {
	cd "${_pkgname}"
  printf "0.0.1" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
	cd st-envixty
  sudo make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}


package() {
	cd st-envixty
  sudo mkdir -p ${pkgdir}/opt/${pkgname}
  sudo cp -rf * ${pkgdir}/opt/${pkgname}
  sudo make PREFIX=/usr DESTDIR="${pkgdir}" install
  sudo install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
  sudo install -Dm644 README.org "${pkgdir}/usr/share/doc/${pkgname}/README.org"
}
