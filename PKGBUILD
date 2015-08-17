# Maintainer : speps <speps at aur dot archlinux dot org>
# Contributor: breakdown <breakdown(at)archlinux(dot)us>

pkgname=plowshare
pkgver=snapshot_git20140112.7ad41c8
pkgrel=1
pkgdesc="Command-line downloader and uploader for Rapidshare, Mediafire and other file sharing websites."
arch=('any')
url="http://code.google.com/p/plowshare/"
license=('GPL')
depends=('curl' 'recode' 'js185')
optdepends=('bash-completion: enable bash auto completion'
            'libcaca: ascii display for no X server'
            'tiv: ascii display for no X server'
            'aview: ascii display for no X server')
conflicts=("$pkgname-git")
source=("http://$pkgname.googlecode.com/files/${pkgname}4-${pkgver/_/-}.tar.gz")
md5sums=('9c31c7f13b41d01bf90563ed25484678')

package() {
  cd "$srcdir/${pkgname}4-${pkgver/_/-}"

  DESTDIR="$pkgdir/" PREFIX=/usr ./setup.sh install

  # bash completion script
  install -Dm644 etc/$pkgname.completion \
    "$pkgdir/usr/share/bash-completion/completions/$pkgname"

  # set CDIR for bash completion
  sed -i "s|local/||" \
    "$pkgdir/usr/share/bash-completion/completions/$pkgname"
}

# vim:set ts=2 sw=2 et:
