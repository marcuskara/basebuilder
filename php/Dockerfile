# Copyright 2015 basebuilder authors. All rights reserved.
# Use of this source code is governed by a BSD-style
# license that can be found in the LICENSE file.

# this file describes how to build tsuru php image
# to run it:
# 1- run: $ tsuru-admin platform-add php -d https://raw.github.com/tsuru/basebuilder/master/php/Dockerfile

from    ubuntu:14.04
run     locale-gen en_US.UTF-8
env     LANG=en_US.UTF-8 LANGUAGE=en_US:en LC_ALL=en_US.UTF-8
run     echo 'deb http://archive.ubuntu.com/ubuntu/ vivid main restricted universe multiverse' >> /etc/apt/sources.list
run     echo 'deb http://archive.ubuntu.com/ubuntu/ vivid-security main restricted universe multiverse' >> /etc/apt/sources.list
run     echo 'APT::Default-Release "trusty";' >> /etc/apt/apt.conf.d/01ubuntu
run	apt-get update
run	apt-get install wget -y --force-yes
run	mkdir /var/lib/tsuru
run	wget --no-check-certificate https://github.com/tsuru/basebuilder/tarball/master -O basebuilder.tar.gz
run	tar -xvf basebuilder.tar.gz -C /var/lib/tsuru --strip 1
run	rm basebuilder.tar.gz
run	cp /var/lib/tsuru/php/deploy /var/lib/tsuru
run	cp /var/lib/tsuru/php/interpretor/fpm5/php5_apt_preferences /etc/apt/preferences.d/php5
run	/var/lib/tsuru/php/install
