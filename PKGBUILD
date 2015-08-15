# $Id:$
# Contributor: Balwinder S "bsd" Dheeman (bdheeman AT gmail.com)
# Maintainer: Balwinder S "bsd" Dheeman (bdheeman AT gmail.com)

pkgname=chromium-browser-l10n-ppa
_pkgname=${pkgname%-ppa}
_pkgver=svn20120105r116462
_pkgpre=18.0.997.0~
_pkgsuf=0ubuntu1~ucd1~natty
pkgver=18.0.997.0.116462
pkgrel=1
pkgdesc="The open-source project behind Google Chrome (Language Localization)"
arch=('any')
url=https://launchpad.net/chromium-browser/
license=('custom:BSD')
depends=("chromium-browser-ppa>=$pkgver")
provides=("${_pkgname}")

case "$CARCH" in
    any|i686|x86_64)
	_bldarch='all'
	md5sums=('ab2d443875c18f0d5d5847179a0cc706');;
    # The following should not happen; provided you're using 'makepkg' ;)
    *) error "Unknown or invalid CARCH=$CARCH"; exit 1
esac

_url=http://ppa.launchpad.net/chromium-daily/ppa/ubuntu/pool/main/c/chromium-browser
source=(${_url}/${_pkgname}_${_pkgpre}${_pkgver}-${_pkgsuf}_${_bldarch}.deb)

build() {
    msg2 "Extracting files..."
    cd "$srcdir"
    ar x ${_pkgname}_${_pkgpre}${_pkgver}-${_pkgsuf}_${_bldarch}.deb
    tar xf data.tar.lzma -C $pkgdir
    msg2 "Making it nice..."
    mkdir -p $pkgdir/usr/share/licenses/${pkgname}
    ln -s /usr/share/doc/${_pkgname}/copyright $pkgdir/usr/share/licenses/${pkgname}/LICENSE.txt
}

# vim:set ts=4 sw=4 et:
