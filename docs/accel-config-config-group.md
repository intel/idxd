
NAME
====

accel-config-config-group - configure individual attributes of a group

SYNOPSIS
========

>     accel-config config-group <device name>/<group name> [<options>]

EXAMPLE
=======

accel-config config-group dsa0/group0.0 --tokens-reserved=1

OPTIONS
=======

`-r; --tokens-reserved=`  
specify the number of badwdith tokens reserved for the use of engines in
the group. The limit of this value must be:

-   The sum of all tokens-reserved for all groups must be less than or
    equal to total badwidth tokens from group capability field of the
    device.

`-t; --tokens-allowed=`  
specify the maxinum number of bandwidth tokens that may be in use at one
time by all engines in the group. This value can be used to limit the
maximum bandwidth used by engines in the group. The limit of this value
must be:

-   greater than 0

-   greater than or equal to the tokens-reserved value for this group.

-   less than or equal to the sum of tokens reserved field and the
    non-reserved bandwidth tokens (total bandwidth tokens - total
    tokens-reserved for all groups).

`-l; --use-token-limit=`  
toggle the enabling of token limt usage. use-token-limit should be
either 0 or 1.

`-a; --traffic-class-a=`  
specify traffic class A for this group, it should be larger than 0 and
less than 8.

`-b; --traffic-class-b=`  
specify traffic class B for this group, it should be larger than 0 and
less than 8.

COPYRIGHT
=========

Copyright (c) 2016 - 2019, Intel Corporation. License GPLv2: GNU GPL
version 2 <http://gnu.org/licenses/gpl.html>. This is free software: you
are free to change and redistribute it. There is NO WARRANTY, to the
extent permitted by law.
