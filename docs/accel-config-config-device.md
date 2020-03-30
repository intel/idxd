
NAME
====

accel-config-config-device - configure the individual attributes of the
device

SYNOPSIS
========

>     accel-config config-device <device name> [<options>]

EXAMPLE
=======

accel-config config-device dsa0 --token-limit=1

OPTIONS
=======

`-l; --token-limit=`  
This specifies the maximum number of bandwidth tokens that may be in use
at one time by operations that access low bandwidth memory. This number
of bandwidth tokens is shared by all descriptors accessing low bandwidth
memory across the entire device. token_limit should be more than 0.

COPYRIGHT
=========

Copyright (c) 2016 - 2019, Intel Corporation. License GPLv2: GNU GPL
version 2 <http://gnu.org/licenses/gpl.html>. This is free software: you
are free to change and redistribute it. There is NO WARRANTY, to the
extent permitted by law.
