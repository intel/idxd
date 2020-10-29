
NAME
====

accel-config-config-wq - configure individual attributes of a work queue

SYNOPSIS
========

>     accel-config config-wq <device name>/<wq name> [<options>]

EXAMPLE
=======

accel-config config-devie dsa0/wq0.0 --wq-size=16

OPTIONS
=======

`-g; --group-id=`  
specify the group id used by work queue, group id should be between 0
and the maximum number of groups per device. A group id of -1
disassociates the work queue from a group.

`-s; --wq-size=`  
specify work queue size used by a work queue. The wq-size should be
between 0 and the maximum workqueue size exposed by the device in the
max\_work\_queue\_size attribute under device.

`-p; --priority`  
specify the priority of this work queue relative to other work queues in
the same group. This field ranges from 1 to 15 where the larger value
means higher priority. For example, if wq1 has a priority of 6 and wq2
has priority of 2, wq1 will issue 3 times as many descriptors to the
engine compare to wq2.

`-b; --block-on-fault`  
toggle block on fault enable for the work queue. block-on-fault should
be either 0 or 1. If block on fault is disabled, if a page fault occurs
on a source or destination memory access, the operation stops and the
page fault is reported to the software.

`-t; --threshold`  
configure the threshold for the wq. The set up threshold value should be
larger than 0 and only for "shared" wq, and note that the configured
threshold value should be at least 1 less than the configured wq-size
value. The reason is threshold is set for unprivileged users, and need
to reserve at least 1 space for the privileged user for commands.

`-y; --type`  
configure the type for the wq. The wq type can be "kernel" for kernel
user case to request wq, "mdev" for mediated device driver use case to
request wq or "user" for regular character device driver use case to wq.

`-m; --mode`  
configure the mode for the wq. The wq mode can be set as "dedicated" or
"shared".

`-c; --max-batch-size`
specify the max batch size used by a work queue. The value should be
between 1 and the device maximum batch size found in the
max\_batch\_size attribute under device. If the value is not a power
of 2, it will be rounded up to the next power of 2.

`-x; --max-transfer-size`
specify the max transfer size used by a work queue. The value should be
between 1 and the device maximum transfer size found in the
max\_transfer\_size attribute under device. If the value is not a power
of 2, it will be rounded up to the next power of 2.

COPYRIGHT
=========

Copyright (c) 2016 - 2019, Intel Corporation. License GPLv2: GNU GPL
version 2 <http://gnu.org/licenses/gpl.html>. This is free software: you
are free to change and redistribute it. There is NO WARRANTY, to the
extent permitted by law.
