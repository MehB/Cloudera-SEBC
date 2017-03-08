
###### Command:
`curl -u hadoop01:cloudera "http://52.35.67.233:7180/api/v2/cm/deployment" > test_deployment_api.json`


###### Result:
```
{
  "timestamp" : "2017-03-08T10:50:12.065Z",
  "clusters" : [ {
    "name" : "MehB-Cluster",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "4264558592"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "829423616"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "3525050368"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "593"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-14-88.us-west-2.compute.internal"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive_password"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-159dda8662ed031b7bd1f4e19d6301f9",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-09b2f5bd2c629a67a"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-3c00c5b4675be1d27dcfc3105af4b787",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0f9dbadbacf67e340"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-6e432c5940fcc0e96096f605f08be442",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0b30bd8b27a5c7527"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-dde693738ba3ac0bd954129afb50ab57",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0f663185c5b85bfcf"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-dfc9876ef27cfbcf983e3cc60f870a85",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-06ea86c975cba2e17"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-159dda8662ed031b7bd1f4e19d6301f9",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "i-09b2f5bd2c629a67a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "d2azpdo6crb6zskls6zr8b8k2"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-3c00c5b4675be1d27dcfc3105af4b787",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "i-0f9dbadbacf67e340"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cqji1t40bp3j817259whnyhvk"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-6e432c5940fcc0e96096f605f08be442",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0b30bd8b27a5c7527"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8uoj4gj87permb3trdv2tcqyl"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-dde693738ba3ac0bd954129afb50ab57",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0f663185c5b85bfcf"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "emge57e56obw73oilaqobzk1h"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-dfc9876ef27cfbcf983e3cc60f870a85",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-06ea86c975cba2e17"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "848chpklpqib5gm3soclh4tu5"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-172-31-14-88.us-west-2.compute.internal"
        }, {
          "name" : "database_password",
          "value" : "hue"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-NAMENODE-159dda8662ed031b7bd1f4e19d6301f9"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-3c00c5b4675be1d27dcfc3105af4b787",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "i-0f9dbadbacf67e340"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1z21157jttlfuggo92gmey0oa"
          }, {
            "name" : "secret_key",
            "value" : "Rtrh3H1Qp5r8BlC1XRgpJ2zFnlKHZ5"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "ip-172-31-14-88.us-west-2.compute.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "829423616"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-3c00c5b4675be1d27dcfc3105af4b787",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "i-0f9dbadbacf67e340"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "231x70npgw2t3edlz78chxk8w"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "6"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "1"
          } ]
        }, {
          "roleType" : "JOBHISTORY",
          "items" : [ {
            "name" : "mr2_jobhistory_java_heapsize",
            "value" : "829423616"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "rm_cpu_shares",
            "value" : "1800"
          }, {
            "name" : "rm_io_weight",
            "value" : "900"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "3"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "3815"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "3815"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "90"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "ZaYfTch5756WsZi5pj8hB9frMPZATs"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-3c00c5b4675be1d27dcfc3105af4b787",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "i-0f9dbadbacf67e340"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bb3upk4vx1m28k3isa76jwigz"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-6e432c5940fcc0e96096f605f08be442",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0b30bd8b27a5c7527"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "29qdov6wkhbc6pmjvmmkanjst"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-dde693738ba3ac0bd954129afb50ab57",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0f663185c5b85bfcf"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "e2u1lmu290jatl8v1o2x7cdgx"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-dfc9876ef27cfbcf983e3cc60f870a85",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-06ea86c975cba2e17"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4dcbbxvlzs5uib6u8tcb0rpnz"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-159dda8662ed031b7bd1f4e19d6301f9",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "i-09b2f5bd2c629a67a"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "50"
          }, {
            "name" : "role_jceks_password",
            "value" : "lapdckqvdf26atgnz8ss3z2p"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "BALANCER",
          "items" : [ {
            "name" : "balancer_java_heapsize",
            "value" : "829423616"
          } ]
        }, {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "832090112"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "200"
          }, {
            "name" : "rm_io_weight",
            "value" : "100"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/dfs/jn"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          }, {
            "name" : "namenode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "role_config_suppression_namenode_java_heapsize_minimum_validator",
            "value" : "true"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "1073741824"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "QyhPI0IPSrc2LR2P4OBa4dJwIhwVA7"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "IjXj3USlgJs3NKTrKMf0BKB7laMcjX"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "f82kfKMFa5WvbFf850LKP1Nu7ivnBU"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "10"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-3c00c5b4675be1d27dcfc3105af4b787",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "i-0f9dbadbacf67e340"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-6e432c5940fcc0e96096f605f08be442",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0b30bd8b27a5c7527"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1ofdv4cfr4jiyffdlism5n8ke"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-dde693738ba3ac0bd954129afb50ab57",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0f663185c5b85bfcf"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2h7d64olcbopgtu19kwcnomr3"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-dfc9876ef27cfbcf983e3cc60f870a85",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-06ea86c975cba2e17"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8crv4es56li6wzh3uciklkfpw"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-159dda8662ed031b7bd1f4e19d6301f9",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-09b2f5bd2c629a67a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5rsgbl997s7ycyld48ucabm7z"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-dde693738ba3ac0bd954129afb50ab57",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-0f663185c5b85bfcf"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3c3yewvlu96vprqxbuukxjoxy"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-6e432c5940fcc0e96096f605f08be442",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0b30bd8b27a5c7527"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dk670bushne7syv8rhuelh1ss"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-dde693738ba3ac0bd954129afb50ab57",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0f663185c5b85bfcf"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7a297ei0l1fap1qbrgcx57u5t"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-dfc9876ef27cfbcf983e3cc60f870a85",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-06ea86c975cba2e17"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7xuu9uu8qktynumveftmfmrzm"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-159dda8662ed031b7bd1f4e19d6301f9",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-09b2f5bd2c629a67a"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "52"
          }, {
            "name" : "role_jceks_password",
            "value" : "78ade24orptffos4orgfz7wy3"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-dde693738ba3ac0bd954129afb50ab57",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-0f663185c5b85bfcf"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "57"
          }, {
            "name" : "role_jceks_password",
            "value" : "8ydjelx31jawyhvxv17yjd0hb"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "i-0f9dbadbacf67e340",
    "ipAddress" : "172.31.14.88",
    "hostname" : "ip-172-31-14-88.us-west-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "host_config_suppression_memory_overcommitted_validator",
        "value" : "true"
      } ]
    }
  }, {
    "hostId" : "i-09b2f5bd2c629a67a",
    "ipAddress" : "172.31.16.8",
    "hostname" : "ip-172-31-16-8.us-west-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0f663185c5b85bfcf",
    "ipAddress" : "172.31.21.227",
    "hostname" : "ip-172-31-21-227.us-west-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "host_config_suppression_memory_overcommitted_validator",
        "value" : "true"
      } ]
    }
  }, {
    "hostId" : "i-0b30bd8b27a5c7527",
    "ipAddress" : "172.31.26.228",
    "hostname" : "ip-172-31-26-228.us-west-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "host_config_suppression_memory_overcommitted_validator",
        "value" : "true"
      } ]
    }
  }, {
    "hostId" : "i-06ea86c975cba2e17",
    "ipAddress" : "172.31.31.1",
    "hostname" : "ip-172-31-31-1.us-west-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "host_config_suppression_memory_overcommitted_validator",
        "value" : "true"
      } ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-3c00c5b4675be1d27dcfc3105af4b787",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "e0729eb343f8be8d2e5158eb052e9b387db186b59fcce245d143eb112d5111c2",
    "pwSalt" : -2114713483960187887,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-3c00c5b4675be1d27dcfc3105af4b787",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "928423a16fff3acfdf7f728fb95086ec5ec204056a79dca5d713beadf2515669",
    "pwSalt" : -524034558270950113,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-3c00c5b4675be1d27dcfc3105af4b787",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "ddd53238683b8db95b60191de1b577a6020ab599921c0256812019a1878fb11f",
    "pwSalt" : -142055401278894103,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-3c00c5b4675be1d27dcfc3105af4b787",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "b08a2cd3404038cf9f9ea1f4240382c9de6f8e1f0ff48a2dbccc4f1e7d286442",
    "pwSalt" : -391701318446015825,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "bc201e3f0723e541efae9a44cc1fb64832802d163b9f67e11b87e6d632d99db9",
    "pwSalt" : 1173589416021730618,
    "pwLogin" : true
  }, {
    "name" : "hadoop01",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "37fdf61b8879be14f7067de6564d76e5a7476eb02f8d9e5f05bda4042722d0c0",
    "pwSalt" : -1124338475788321115,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "edb28bac738b53b5b5cfeff2b84cbca6ac168708a789ecc870267a92de8069b5",
    "pwSalt" : 1782013656200649374,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.8.3",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20161019-1014",
    "gitHash" : "518f0d6d44abc87bc392646e4369a20c8192b7cf",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "EVENTSERVER",
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "829423616"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-14-88.us-west-2.compute.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman_password"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "829423616"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-3c00c5b4675be1d27dcfc3105af4b787",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "i-0f9dbadbacf67e340"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "9r8qxhfsxoo44ljeci0bxh83e"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-3c00c5b4675be1d27dcfc3105af4b787",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "i-0f9dbadbacf67e340"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "d8x461xx2w1n2k8q7fc6bbpjj"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-3c00c5b4675be1d27dcfc3105af4b787",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "i-0f9dbadbacf67e340"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "8i3e7e72i03sbokypnl3bixw6"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-3c00c5b4675be1d27dcfc3105af4b787",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "i-0f9dbadbacf67e340"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "97xbn7w4kdcx936l6qi8b25gi"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-3c00c5b4675be1d27dcfc3105af4b787",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "i-0f9dbadbacf67e340"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "93jf4jb4cgno4u0aye1mvs0eo"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/25/2012 3:40"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/5.8.3/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    } ]
  }
}
```
