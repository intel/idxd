
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
        "max_groups":4,
        "max_work_queues":8,
        "max_engines":4,
        "work_queue_size":64,
        "numa_node":0,
        "errors":[
          "0",
          "0",
          "0",
          "0"
        ],
        "op_cap":"0x1003f03ff",
        "state":"disabled",
        "max_tokens":64,
        "max_batch_size":512,
        "ims_size":256,
        "max_transfer_size":2147483648,
        "configurable":1,
        "pasid_enabled":1,
        "token_limit":0,
        "cdev_major":241,
        "groups":[
          {
            "dev":"group0.1",
            "engines":[
              {
                "dev":"engine0.3",
                "group_id":1
              },
              {
                "dev":"engine0.2",
                "group_id":1
              }
            ],
            "work_queues":"wq0.1 ",
            "workqueues":[
              {
                "dev":"wq0.1",
                "mode":"dedicated",
                "size":8,
                "group_id":1,
                "priority":10,
                "priv":1,
                "block_on_fault":"1"
              }
            ]
          },
          {
            "dev":"group0.3",
            "engines":"",
            "work_queues":""
          },
          {
            "dev":"group0.0",
            "engines":[
              {
                "dev":"engine0.1",
                "group_id":0
              },
              {
                "dev":"engine0.0",
                "group_id":0
              }
            ],
            "work_queues":"wq0.0 ",
            "workqueues":[
              {
                "dev":"wq0.0",
                "mode":"shared",
                "size":16,
                "group_id":0,
                "priority":10,
                "priv":1,
                "block_on_fault":"1"
              }
            ]
          },
          {
            "dev":"group0.2",
            "engines":"",
            "work_queues":""
          }
        ],
        "non_grouped_workqueues":[
          {
            "dev":"wq0.2",
            "mode":"shared",
            "size":0,
            "group_id":-1,
            "priority":0,
            "priv":0,
            "block_on_fault":"0"
          },
          {
            "dev":"wq0.4",
            "mode":"shared",
            "size":0,
            "group_id":-1,
            "priority":0,
            "priv":0,
            "block_on_fault":"0"
          },
          {
            "dev":"wq0.6",
            "mode":"shared",
            "size":0,
            "group_id":-1,
            "priority":0,
            "priv":0,
            "block_on_fault":"0"
          },
          {
            "dev":"wq0.3",
            "mode":"shared",
            "size":0,
            "group_id":-1,
            "priority":0,
            "priv":0,
            "block_on_fault":"0"
          },
          {
            "dev":"wq0.7",
            "mode":"shared",
            "size":0,
            "group_id":-1,
            "priority":0,
            "priv":0,
            "block_on_fault":"0"
          }
        ]
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
Include workqueue info in the listing

`-E; --engines`  
Include engine info in the listing

TO BE CHANGED -i:: --idle:: Include idle (not enabled) devices in the
listing

COPYRIGHT
=========

Copyright (c) 2016 - 2019, Intel Corporation. License GPLv2: GNU GPL
version 2 <http://gnu.org/licenses/gpl.html>. This is free software: you
are free to change and redistribute it. There is NO WARRANTY, to the
extent permitted by law.
