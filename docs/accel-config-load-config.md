﻿
NAME
====

accel-config-load-config - load pre-defined the configuration in json
format

SYNOPSIS
========

>     accel-config load-config [<options>]

Load and scan through the pre-defined configuration file in json format,
and set the configured attribute into corresponding component.

There is a sample config file at
/etc/accel-config/accel-config.conf.sample, and it can be used as a
reference for user about how the loadable config file looks like, but it
should not be used directly given the variance of each system. The user
should create a proper config file according to the format of sample
file and use "-c" option to point to the config file.

EXAMPLE
=======

    # accel-config load-config
    The command will load the default config file at
    /etc/accel-config/accel-config.conf

    # accel-config load-config -c <my_config.conf>
    The command will load the specified config file

OPTIONS
=======

`-l; --log=`  
to set where to output the config’s notification

`-c; --config-file`  
to specify the location of the customized config file
