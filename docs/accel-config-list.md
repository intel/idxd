
NAME
====

accel-config-list - display the platform accfg device(s) topology and
attributes in json format

SYNOPSIS
========

>     accel-config list [<options>]

List all the DSA devices discovered by the driver and the driver
exported attributes.

Options can be specified to limit the output to devices of a certain
grouping where the grouping are devices, groups, work queues and
engines. By default, *accel-config list* with no options is equivalent
to:

>     accel-config list --devices --engines --groups --workqueues

EXAMPLE
=======
# accel-config list  
    [
    {
    "dev":"dsa0",
    "token_limit":0,
    "max_groups":4,
    "max_work_queues":8,
    "max_engines":4,
    "work_queue_size":64,
    "numa_node":-1,
    "op_cap":"0x1003f03ff",
    "state":"enabled",
    "max_tokens":64,
    "max_batch_size":512,
    "max_transfer_size":2147483648,
    "configurable":1,
    "pasid_enabled":1,
    "cdev_major":247,
    "clients":2,
    "groups":[
      {
        "dev":"group0.0",
        "tokens_reserved":0,
        "use_token_limit":0,
        "tokens_allowed":0,
        "traffic_class_a":-1,
        "traffic_class_b":-1,
        "grouped_workqueues":[
          {
            "dev":"wq0.0",
            "mode":"shared",
            "size":16,
            "group_id":0,
            "priority":10,
            "block_on_fault":1,
            "cdev_minor":0,
            "type":"user",
            "name":"app1",
            "threshold":15,
            "state":"enabled",
            "clients":1
          }
        ],
        "grouped_engines":[
          {
            "dev":"engine0.0",
            "group_id":0
          },
          {
            "dev":"engine0.1",
            "group_id":0
          }
        ]
      },
      {
        "dev":"group0.1",
        "tokens_reserved":0,
        "use_token_limit":0,
        "tokens_allowed":0,
        "traffic_class_a":-1,
        "traffic_class_b":-1,
        "grouped_workqueues":[
          {
            "dev":"wq0.1",
            "mode":"dedicated",
            "size":16,
            "group_id":1,
            "priority":10,
            "block_on_fault":1,
            "cdev_minor":1,
            "type":"user",
            "name":"app2",
            "threshold":0,
            "state":"enabled",
            "clients":1
          }
        ],
        "grouped_engines":[
          {
            "dev":"engine0.2",
            "group_id":1
          },
          {
            "dev":"engine0.3",
            "group_id":1
          }
        ]
      },
      {
        "dev":"group0.2",
        "tokens_reserved":0,
        "use_token_limit":0,
        "tokens_allowed":0,
        "traffic_class_a":-1,
        "traffic_class_b":-1
      },
      {
        "dev":"group0.3",
        "tokens_reserved":0,
        "use_token_limit":0,
        "tokens_allowed":0,
        "traffic_class_a":-1,
        "traffic_class_b":-1
      }
    ]


OPTIONS
=======

`-d; --device=`  
A accfg device name like dsa{number}. Filter listing by devices that
reference the given device.

`-g; --group=`  
An *groupX.Y* group name, or device id plus group id tuple *X.Y*. Limit
the group list to the single identified device if present.

`-q; --workqueue=`  
An *wqX.Y* workqueue name, or device id plus workqueue id tuple *X.Y*.
Limit the workqueue list to the single identified device if present.

`-e; --engine=`  
An *engineX.Y* engine name, or device id plus engine id tuple *X.Y*.
Limit the engine list to the single identified device if present.

`-D; --devices`  
Include device info in the listing

`-G; --regions`  
Include group info in the listing

`-Q; --workqueues`  
Include active workqueue info in the listing

`-E; --engines`  
Include both idle (not enabled) and active engine info in the listing

TO BE CHANGED -i:: --idle:: Include idle (not enabled) devices in the
listing

COPYRIGHT
=========

Copyright (c) 2016 - 2019, Intel Corporation. License GPLv2: GNU GPL
version 2 <http://gnu.org/licenses/gpl.html>. This is free software: you
are free to change and redistribute it. There is NO WARRANTY, to the
extent permitted by law.
