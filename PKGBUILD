# Maintainer: Nano77 <nanoarch77@gmail.com>
# Last update: 11/18/11


pkgname=gnome-shell-theme-selector
pkgver=20111214
pkgrel=1
pkgdesc="A GUI to set GnomeShell Theme"
arch=(any)
license=('GPL')
url="http://github.com/Nano77/gnome-shell-theme-selector"
depends=('gnome-shell-native-theme')
makedepends=('git')
optdepends=('gdm3setup-native-theme: Select the GDM GnomeShell Theme')


_gitroot="git://github.com/Nano77/gnome-shell-theme-selector.git"
_gitname="gnome-shell-theme-selector"

build() {
  cd ${srcdir}

  msg "Connecting to GIT server..."
  if [[ -d ${_gitname} ]]; then
    (cd ${_gitname} && git pull origin)
  else
    git clone ${_gitroot} ${_gitname}
  fi
  msg "GIT checkout done or server timeout"

}

package() {
	cd ${srcdir}/gnome-shell-theme-selector

	install --mode=755 -D gnome-shell-theme-selector.py ${pkgdir}/usr/bin/gnome-shell-theme-selector.py
	install -D gnome-shell-theme-selector.desktop ${pkgdir}/usr/share/applications/gnome-shell-theme-selector.desktop

}
