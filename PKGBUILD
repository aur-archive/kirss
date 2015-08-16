# Maintainer:  TDY <tdy@archlinux.info>
# Contributor: Nathan Jones <nathanj@insightbb.com>

pkgname=kirss
pkgver=0.8.1
pkgrel=1
pkgdesc="A simple RSS aggregator that outputs an HTML file"
arch=('any')
url="http://github.com/nathanj/kirss/"
license=('BSD')
depends=('python2>=2.5')
source=("http://home.insightbb.com/~nathanj/kirss/$pkgname-$pkgver.tar.gz")
md5sums=('330f73b4bd6f25fd056b97fa9973a311')

build() {
  cd "$srcdir/$pkgname-$pkgver"
  sed -i 's+man/+share/&+; 15 s+\.py++' setup.py
  ln -sf $pkgname.py $pkgname
  python2 setup.py build
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  python2 setup.py install --prefix=/usr --root="$pkgdir" --optimize=1
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

# vim:set ts=2 sw=2 et:
