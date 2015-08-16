# Contributor: MeMi69 <MetalMilitia@gmx.net>

pkgname=haveclip
pkgver=0.12.1
pkgrel=1
license=('GPL')
pkgdesc="A simple clipboard manage and synchronization tool "
url="http://www.havefun.cz/projects/haveclip/"
depends=('qt4')
arch=('i686' 'x86_64')
source=(http://downloads.sourceforge.net/haveclip/$pkgname-desktop-$pkgver-src.tar.gz
       haveclip.desktop
       haveclip.png)

md5sums=('f067ff57f591cd608277b92f7ecc01fa'
         '5b23858fd7e2f11bd312464331d481c8'
         '383970eb2d819d67e96623bb8b0b33a4')
build() {
  cd "$srcdir/$pkgname-desktop-$pkgver-src"
  qmake
  make || return 1
}  

package() {
  install -Dm644 haveclip.desktop "$pkgdir/usr/share/applications/kde4/haveclip.desktop"
  install -Dm644 haveclip.png "$pkgdir/usr/share/icons/haveclip.png"
  cd "$srcdir/$pkgname-desktop-$pkgver-src/bin"
  install -Dm755 haveclip "$pkgdir/usr/bin/haveclip"
  cd "$srcdir/$pkgname-desktop-$pkgver-src/haveclip-core/bin"
  install -Dm755 libhaveclipcore.so.1 "$pkgdir/usr/lib/libhaveclipcore.so.1" 
}
