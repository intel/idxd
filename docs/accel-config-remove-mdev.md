
NAME
====

accel-config-remove-mdev - clear the uuid from a workqueue uuid list. If
not uuid is specified, then entire uuid list in this workqueue will be
removed.

SYNOPSIS
========

>     accel-config remove-mdev <device name>/<workqueue name> [<options>]

EXAMPLE
=======

accel-config remove-mdev dsa0/wq0.0
--uuid=0f34f0ed-6f67-4086-a4b7-8e1ecf077dce

OPTIONS
=======

`-u; --uuid=`  
remove this specific uuid from uuid list in the specified workqueue.

COPYRIGHT
=========

Copyright (c) 2016 - 2019, Intel Corporation. License GPLv2: GNU GPL
version 2 <http://gnu.org/licenses/gpl.html>. This is free software: you
are free to change and redistribute it. There is NO WARRANTY, to the
extent permitted by law.
