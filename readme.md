TCNative Packager
-----------------

Simple script to help you create an RPM package of the Apache TCnative system. This is an option to improve tomcat performance but OS packages aren't provided. This works with both OpenJDK and Oracle/Sun JDK by autodetecting what you already have installed. If both are installed Oracle/Sun is used. Arch is also autodetected and post install sym links are automatically created for the Oracle/Sun JDK installation. If you are root the build env is automatically assured, if not you are given hints on what packages to install. Reference developement platform was CentOS 6.6 64bit but should work fine with 7.x as well.

* Source: https://github.com/bryanandrews/tcnative-packager

Example:
~~~
$ ./tcnative-packager.sh 
Ensuring CentOS dependant packages...
  - You are not root, so make sure all your dependancies are already installed like apr-devel openssl-devel apr apr-util apr-util-devel openssl wget, an OpenJDK, and fpm via gem
Detected fpm installed
OpenJDK detected. Version:
openjdk version "1.8.0_45"
OpenJDK Runtime Environment (build 1.8.0_45-b13)
OpenJDK 64-Bit Server VM (build 25.45-b02, mixed mode)
Using JDK found at /usr/lib/jvm/java-openjdk
Creating /home/example/tcnative-packager/src-26944/usr to install and package from
Running configure...
Compiling...
Installing into "/home/example/tcnative-packager/src-26944/usr"...
Setting workdir {:workdir=>"/tmp", :level=>:info}
Setting from flags: architecture=x86_64 {:level=>:info}
Setting from flags: description=The mission of the Tomcat Native Library (TCN) is to provide a free library of C data structures and routines.  This library contains additional utility interfaces for Java. {:level=>:info}
Setting from flags: epoch= {:level=>:info}
Setting from flags: iteration=0 {:level=>:info}
Setting from flags: license=Apache Software License {:level=>:info}
Setting from flags: maintainer=you@example.com {:level=>:info}
Setting from flags: name=tcnative {:level=>:info}
Setting from flags: url=http://tomcat.apache.org/download-native.cgi {:level=>:info}
Setting from flags: version=1.1.33 {:level=>:info}
Setting from flags: architecture=x86_64 {:level=>:info}
Converting dir to rpm {:level=>:info}
no value for epoch is set, defaulting to nil {:level=>:warn}
Reading template {:path=>"/usr/local/rvm/gems/ruby-2.2.0/gems/fpm-1.3.3/templates/rpm.erb", :level=>:info}
no value for epoch is set, defaulting to nil {:level=>:warn}
Running rpmbuild {:args=>["rpmbuild", "-bb", "--define", "buildroot /tmp/package-rpm-build20150615-27597-r98ysc/BUILD", "--define", "_topdir /tmp/package-rpm-build20150615-27597-r98ysc", "--define", "_sourcedir /tmp/package-rpm-build20150615-27597-r98ysc", "--define", "_rpmdir /tmp/package-rpm-build20150615-27597-r98ysc/RPMS", "--define", "_tmppath /tmp", "/tmp/package-rpm-build20150615-27597-r98ysc/SPECS/tcnative.spec"], :level=>:info}
Executing(%prep): /bin/sh -e /tmp/rpm-tmp.AnyiY3 {:level=>:info}
Executing(%build): /bin/sh -e /tmp/rpm-tmp.FK6xnN {:level=>:info}
Executing(%install): /bin/sh -e /tmp/rpm-tmp.Vso6Mw {:level=>:info}
Processing files: tcnative-1.1.33-0.x86_64 {:level=>:info}
Wrote: /tmp/package-rpm-build20150615-27597-r98ysc/RPMS/x86_64/tcnative-1.1.33-0.x86_64.rpm {:level=>:info}
Executing(%clean): /bin/sh -e /tmp/rpm-tmp.npuzT2 {:level=>:info}
Created package {:path=>"../tcnative-1.1.33-0.x86_64.rpm"}
Done!
Cleaning up /home/io/tcnative-packager/src-26944/usr...
########################################################

Name        : tcnative                     Relocations: / 
Version     : 1.1.33                            Vendor: io@example.com
Release     : 0                             Build Date: Mon 15 Jun 2015 09:23:19 AM MST
Install Date: (not installed)               Build Host: me.example.com
Group       : default                       Source RPM: tcnative-1.1.33-0.src.rpm
Size        : 2567110                          License: Apache Software License
Signature   : (none)
Packager    : you@example.com
URL         : http://tomcat.apache.org/download-native.cgi
Summary     : The mission of the Tomcat Native Library (TCN) is to provide a free library of C data structures and routines.  This library contains additional utility interfaces for Java.
Description :
The mission of the Tomcat Native Library (TCN) is to provide a free library of C data structures and routines.  This library contains additional utility interfaces for Java.
/usr/lib64/libtcnative-1.a
/usr/lib64/libtcnative-1.la
/usr/lib64/libtcnative-1.so
/usr/lib64/libtcnative-1.so.0
/usr/lib64/libtcnative-1.so.0.1.33
/usr/lib64/pkgconfig/tcnative-1.pc
~~~
