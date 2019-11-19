
NAME
====

accel-config-config-engine - configure individual attributes of an
engine

SYNOPSIS
========

>     accel-config config-engine <device name>/<engine name> [<options>]

EXAMPLE
=======

accel-config config-engine dsa0/engine1.2 --group-id=0

OPTIONS
=======

`-g; --group-id=`  
specify the group-id for this engine, group-id should be between 0 and
the maximum number of groups per device shown in max\_groups attribute
under a device. A value of -1 disassociates the engine from any group.

COPYRIGHT
=========

Copyright (c) 2016 - 2019, Intel Corporation. License GPLv2: GNU GPL
version 2 <http://gnu.org/licenses/gpl.html>. This is free software: you
are free to change and redistribute it. There is NO WARRANTY, to the
extent permitted by law.
