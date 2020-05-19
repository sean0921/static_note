# Static build note on Debian GNU/Linux 9

## Why Debian GNU/Linux 9?

* use the latest glibc version that still support GNU/Linux 2.6.32 binary

* more lightweight than RHEL/CentOS distribution

* Debian Stretch is still supported.  After Debian Stretch is EOL, I may consider test it on CentOS 7 or drop 2.6.32 binary support

## Package note

### ncurses

* repo link: 
  * Unofficial, but git VCS supported: https://github.com/mirror/ncurses.git
  * Official download site: https://invisible-mirror.net/archives/ncurses

* configuration:
  * prefix: `/opt/ncurses`
  * parameters: `./configure --prefix=/opt/ncurses --enable-widec LDFLAGS="-static"`
  
### htop

* repo link: https://github.com/hishamhm/htop.git
* configuration:
  * parameters: `./configure CFLAGS="-I/opt/ncurses/include" LDFLAGS="-L/opt/ncurses/lib --static"`
