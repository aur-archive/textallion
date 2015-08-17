# Contributor: Stefan Husmann 
# Maintainer: Eric Forgeot < http://esclinux.tk >

pkgname=textallion
pkgver=2013_07_28
pkgrel=2
pkgdesc="A simple word processor based on txt2tags and its markup, for publishing prose, literature, poetry in HTML, PDF or EPUB, and also cyoa (gamebooks & renpy)"
arch=('any')
url="http://anamnese.online.fr/site2/textallion/docs/presentation.html"
license=('BSD')
depends=('python2')
makedepends=('gzip')
optdepends=('texlive-humanities: export to pdf' 'calibre: export to epub' 'tidyhtml: cleaning html for epub export' 'psutils: advanced postscript operations like making booklets' 'ttf-linux-libertine: xetex optional backend' 'imagemagick: generate personalised covers' 'perl: for renpy export' 'gnome-inform7: for z-code export')
source=(http://textallion.googlecode.com/files/textallion_2013-07-28_valadon.zip )

sha1sums=('1bd9367a112933e8658f6971be356dd966ff540f')

build() {
  cd $srcdir/${pkgname}
    	mkdir -p $pkgdir/usr/bin/
	mkdir -p $pkgdir/usr/share/${pkgname}
	cp -fr $srcdir/${pkgname}/* $pkgdir/usr/share/${pkgname}
	rm $pkgdir/usr/share/${pkgname}/textallion_install.sh
	chmod -R 755 $pkgdir/usr/share/textallion/
	chmod +x $pkgdir/usr/share/textallion/core/textallion.sh
	chmod +x $pkgdir/usr/share/textallion/contrib/txt2tags/txt2tags

    echo "sh /usr/share/textallion/core/textallion.sh" > $pkgdir/usr/bin/textallion
    chmod +x $pkgdir/usr/bin/textallion
    
    #desktop icons
	mkdir -p $pkgdir/usr/share/pixmaps
	cp $srcdir/${pkgname}/media/icon_textallion256.png $pkgdir/usr/share/pixmaps/textallion.png
	install -D -m644 $srcdir/${pkgname}/contrib/others/textallion.desktop $pkgdir/usr/share/applications/textallion.desktop
    
    
}
