# $Id: PKGBUILD 80362 2012-11-20 18:55:18Z tomegun $
# Contributor: Chris Brannon <chris@the-brannons.com>
# Contributor: Kyle <kyle@gmx.ca>
pkgname=espeakup
pkgver=0.71
pkgrel=7
pkgdesc='Allows the Speakup screen review system to use the ESpeak synthesizer.'
arch=('i686' 'x86_64')
url="http://github.com/williamh/espeakup"
license=('GPL3')
#source=("ftp://linux-speakup.org/pub/linux/goodies/${pkgname}-${pkgver}.tar.bz2"
# temporary location
source=("http://the-brannons.com/espeakup-0.71.tar.bz2"
        espeakup espeakup.conf.d espeakup.service espeakup.modules-load.d)
depends=(speakup-utils espeak)
backup=(etc/conf.d/espeakup)

build() {
  cd "$srcdir/$pkgname-$pkgver"
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make DESTDIR="${pkgdir}" install 
  install -m755 -D "${srcdir}/espeakup" "${pkgdir}/etc/rc.d/espeakup"
  install -m644 -D "${srcdir}/espeakup.conf.d" "${pkgdir}/etc/conf.d/espeakup"
  install -m644 -D "${srcdir}/espeakup.service" "${pkgdir}/usr/lib/systemd/system/espeakup.service"
  install -m644 -D "${srcdir}/espeakup.modules-load.d" "${pkgdir}/usr/lib/modules-load.d/espeakup.conf"
}
md5sums=('03daa70b3db3f4f6fbb42c2ee428eda7'
         '7cf0abd493710ed924b7bb7c8d279fb3'
         '0f93974845b15efa12f5e7a74cc0eecd'
         '2c80525983a700d3763d4c90c3ab79a8'
         '75eb512d510d6701b6f63390475dd34f')
