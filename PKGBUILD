pkgname=django-toolbox
pkgver=20101211
pkgrel=1
pkgdesc='Django Toolbox for django-nonrel.'
license=('unknown')
arch=('any')
depends=('django-nonrel')
makedepends=('django-nonrel' 'python2')
url="https://github.com/aparo/djangotoolbox"

_gitroot=git://github.com/aparo/djangotoolbox.git
_gitname=djangotoolbox

build() {
	cd $srcdir

	msg "Connecting to git.freedesktop.org GIT server...."

	if [ -d $startdir/src/$_gitname ] ; then
		cd $_gitname && git-pull origin
		msg "The local files are updated."
	else
		git clone $_gitroot
	fi

	msg "GIT checkout done or server timeout"

	cd "$srcdir/$_gitname"
	python2 setup.py build
}

package() {
	cd "$srcdir/$_gitname"
	python2 setup.py install --root=$pkgdir --optimize=1
}
