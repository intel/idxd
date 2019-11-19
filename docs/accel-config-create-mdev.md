
NAME
====

accel-config-create-mdev - create mdev to a specified workqueue by
generating a random uuid and writing to workqueue sysfs. The workqueue
has to be enabled before running this command and it has to be
configured as "mdev" type. If the workqueue type is shared, this command
can be issued multiple times. If the workqueue is dedicated, only one
uuid is allowed to be created. If this command is issued to a dedicated
wq with uuid already existing, it will trigger operation not permitted
error.

SYNOPSIS
========

>     accel-config create-mdev <device name>/<workqueue name>

EXAMPLE
=======

accel-config create-mdev dsa0/wq0.0

COPYRIGHT
=========

Copyright (c) 2016 - 2019, Intel Corporation. License GPLv2: GNU GPL
version 2 <http://gnu.org/licenses/gpl.html>. This is free software: you
are free to change and redistribute it. There is NO WARRANTY, to the
extent permitted by law.
