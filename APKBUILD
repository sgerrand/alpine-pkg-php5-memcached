# Contributor: Sasha Gerrand <alpine-pkgs@sgerrand.com>
# Maintainer: Sasha Gerrand <alpine-pkgs@sgerrand.com>
_php=php5
pkgname=$_php-memcached
_pkgrealname=memcached
pkgver=2.2.0
pkgrel=0
pkgdesc="PHP extension for interfacing with memcached via libmemcached library"
url="http://pecl.php.net/memcached"
arch="all"
license="PHP"
depends="libmemcached"
depends_dev="$_php-dev"
makedepends="$depends_dev autoconf libmemcached-dev zlib-dev"
install=""
subpackages="$pkgname-dev $pkgname-doc"
source="http://pecl.php.net/get/$_pkgrealname-$pkgver.tgz"

builddir="$srcdir"/$_pkgrealname-$pkgver

build() {
	cd "$builddir"
	phpize || return 1
	./configure --prefix=/usr \
		--disable-memcached-sasl \
	|| return 1
	make || return 1
}

package() {
	cd "$builddir"
	make INSTALL_ROOT="$pkgdir"/ install || return 1
	install -d "$pkgdir"/etc/$_php/conf.d || return 1
	echo "extension=$_pkgrealname.so" > "$pkgdir"/etc/$_php/conf.d/$_pkgrealname.ini
	for _dev in *.h; do
		install -Dm644 $_dev $pkgdir/usr/include/$pkgname/$_dev
	done
	for _doc in CREDITS Changelog; do
		install -Dm644 $_doc $pkgdir/usr/share/doc/$pkgname/$_doc
	done
	install -Dm644 LICENSE $pkgdir/usr/share/licenses/$pkgname/LICENSE
}

md5sums="28937c6144f734e000c6300242f44ce6  memcached-2.2.0.tgz"
sha256sums="17b9600f6d4c807f23a3f5c45fcd8775ca2e61d6eda70370af2bef4c6e159f58  memcached-2.2.0.tgz"
sha512sums="61207d3f8c11b0620dbcb20fb2ebb6d1fc10159a7e879ee91556a303c3dcdf3d2571e8dda5efcbed77ff779f5c9b226aa48800630b9e7781cd964126b848c356  memcached-2.2.0.tgz"
