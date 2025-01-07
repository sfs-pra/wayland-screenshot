pkgname=wayland-screenshot-yad
_pkgname=wayland-screenshot
pkgver=2025.01
pkgrel=07
pkgdesc="A tool to take screenshots on Wayland (yad)"
arch=('any')
url="https://github.com/sfs-pra/wayland-screenshot"
license=('GPL3')
depends=('yad' 'grim' 'wl-clipboard' 'swappy' 'slurp')
optdepends=('sway' 'jq' )
source=("git+https://github.com/sfs-pra/wayland-screenshot.git")
sha256sums=('SKIP')

package() {
  cd "$srcdir/$_pkgname"

  # Install the script
  install -Dm755 wayland-screenshot -t "$pkgdir/usr/bin/"

  # Install the .desktop file
  install -Dm644 wayland-screenshot.desktop -t "$pkgdir/usr/share/applications/"
  install -Dm644 README.md -t "$pkgdir/usr/share/doc/$pkgname/"

  mkdir -p $pkgdir/usr/share/locale/{be,ja,ru,br}/LC_MESSAGES

  # Compile .po files to .mo files
  msgfmt po/be.po -o "$pkgdir/usr/share/locale/be/LC_MESSAGES/wayland-screenshot.mo"
  msgfmt po/ja.po -o "$pkgdir/usr/share/locale/ja/LC_MESSAGES/wayland-screenshot.mo"
  msgfmt po/ru.po -o "$pkgdir/usr/share/locale/ru/LC_MESSAGES/wayland-screenshot.mo"
  msgfmt po/br.po -o "$pkgdir/usr/share/locale/br/LC_MESSAGES/wayland-screenshot.mo"
}
