```sh
[hduser@elephant ~]$ curl -u ahuertaf:password 'http://localhost:7180/api/v2/cm/deployment'
{
  "timestamp" : "2017-11-30T17:11:07.170Z",
  "clusters" : [ {
    "name" : "ahuertaf",
    "version" : "CDH5",
    "services" : [ {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "enableSecurity",
          "value" : "true"
        } ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-321c76da0c8f8ff09f458699ad2b212f",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "bcea8950-6ce9-4d99-9c3b-7ed35b9be24b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8uczcmq4s07zu94f85e6qkk6t"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-d68202787ca4addfa2b7296896a014a4",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "fbdc75d3-ee6a-49b4-aa6f-d5c9b12cac26"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "c4h8zpemjuc2qgyjnafwt8unr"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-fa759e657729c2e98a32b68fb45420a8",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "eaeb4c3a-cb21-456f-9b40-390c81cbef8b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "29wnziaif6e338aaxgcvsxe1f"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "elephant"
          }, {
            "name" : "oozie_database_password",
            "value" : "password"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "test"
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
        "name" : "oozie-OOZIE_SERVER-d68202787ca4addfa2b7296896a014a4",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "fbdc75d3-ee6a-49b4-aa6f-d5c9b12cac26"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9130qbxds2nd03dmks2efx5qj"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "elephant"
        }, {
          "name" : "database_password",
          "value" : "hue_password"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-54f6ad13c3cf4d65d3c77af202f5f8db"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_LOAD_BALANCER-321c76da0c8f8ff09f458699ad2b212f",
        "type" : "HUE_LOAD_BALANCER",
        "hostRef" : {
          "hostId" : "bcea8950-6ce9-4d99-9c3b-7ed35b9be24b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3ukl46uqmm3dys42ginlmuco5"
          } ]
        }
      }, {
        "name" : "hue-HUE_LOAD_BALANCER-fa759e657729c2e98a32b68fb45420a8",
        "type" : "HUE_LOAD_BALANCER",
        "hostRef" : {
          "hostId" : "eaeb4c3a-cb21-456f-9b40-390c81cbef8b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3mrmqmfjdlymrob8uvqlsqu6e"
          } ]
        }
      }, {
        "name" : "hue-HUE_SERVER-321c76da0c8f8ff09f458699ad2b212f",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "bcea8950-6ce9-4d99-9c3b-7ed35b9be24b"
        },
        "config" : {
          "items" : [ {
            "name" : "navmetadataserver_cmdb_password",
            "value" : "4f126b53-fa51-4557-ad32-a957a89f43d8"
          }, {
            "name" : "role_jceks_password",
            "value" : "8k6724i2zdi1x3fr80x32mgmh"
          }, {
            "name" : "secret_key",
            "value" : "sKGSx75pGTlnxUzM3gePgFcMgpiTTS"
          } ]
        }
      }, {
        "name" : "hue-HUE_SERVER-fa759e657729c2e98a32b68fb45420a8",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "eaeb4c3a-cb21-456f-9b40-390c81cbef8b"
        },
        "config" : {
          "items" : [ {
            "name" : "navmetadataserver_cmdb_password",
            "value" : "e3d45582-536f-45f9-8c95-3dc658432424"
          }, {
            "name" : "role_jceks_password",
            "value" : "b7i59622kr3awohiiz0ttly08"
          }, {
            "name" : "secret_key",
            "value" : "mTF0muSI3IV03GcnzzyZDaTXxQyGdh"
          } ]
        }
      }, {
        "name" : "hue-KT_RENEWER-321c76da0c8f8ff09f458699ad2b212f",
        "type" : "KT_RENEWER",
        "hostRef" : {
          "hostId" : "bcea8950-6ce9-4d99-9c3b-7ed35b9be24b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "922nazq9th8lo6e820pvvptxm"
          } ]
        }
      }, {
        "name" : "hue-KT_RENEWER-fa759e657729c2e98a32b68fb45420a8",
        "type" : "KT_RENEWER",
        "hostRef" : {
          "hostId" : "eaeb4c3a-cb21-456f-9b40-390c81cbef8b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5v22bseybkh5xqvg8sq1sc0wb"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/data/disk0/dfs/dn,/data/disk1/dfs/dn"
          }, {
            "name" : "dfs_datanode_data_dir_perm",
            "value" : "700"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "8441707724"
          }, {
            "name" : "dfs_datanode_failed_volumes_tolerated",
            "value" : "1"
          }, {
            "name" : "dfs_datanode_http_port",
            "value" : "1006"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4296015872"
          }, {
            "name" : "dfs_datanode_port",
            "value" : "1004"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "400"
          }, {
            "name" : "rm_io_weight",
            "value" : "200"
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
            "value" : "/data/disk0/dfs/jn"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/data/disk0/dfs/nn,/data/disk1/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/data/disk0/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "3801088000"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_encrypt_data_transfer_algorithm",
          "value" : "AES/CTR/NoPadding"
        }, {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "LvQwn5wLC1h9KQ3ToTfMcwFCiWfIpN"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "sZZm57zKBIiGnx6OyJ9oLhpu4VyuRg"
        }, {
          "name" : "hadoop_secure_web_ui",
          "value" : "true"
        }, {
          "name" : "hadoop_security_authentication",
          "value" : "kerberos"
        }, {
          "name" : "hadoop_security_authorization",
          "value" : "true"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "bQdbqGbfvWV5TzTj8EIm0CAAS8JVZe"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "20"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-54f6ad13c3cf4d65d3c77af202f5f8db",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "680beb84-8d4b-4b9d-8260-e28b2cee0eb8"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-21cc8e9abc6672a60a5eedcad444875a",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "82199bcc-1891-4a8c-bfd9-444769d49151"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4vcjawoaw6qr6yza6i98ct930"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-321c76da0c8f8ff09f458699ad2b212f",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "bcea8950-6ce9-4d99-9c3b-7ed35b9be24b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "a9217v8368yy2315ersiciain"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-d68202787ca4addfa2b7296896a014a4",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "fbdc75d3-ee6a-49b4-aa6f-d5c9b12cac26"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dak5wrqivh6kau5b781hc5tlx"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-fa759e657729c2e98a32b68fb45420a8",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "eaeb4c3a-cb21-456f-9b40-390c81cbef8b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1gymcuzwqsnlmj3t70qrv6rzt"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-54f6ad13c3cf4d65d3c77af202f5f8db",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "680beb84-8d4b-4b9d-8260-e28b2cee0eb8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4sbxuvekila1t0344odq60hvw"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-fa759e657729c2e98a32b68fb45420a8",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "eaeb4c3a-cb21-456f-9b40-390c81cbef8b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1ye4qe2aiv882i3x2s0iel2ok"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-54f6ad13c3cf4d65d3c77af202f5f8db",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "680beb84-8d4b-4b9d-8260-e28b2cee0eb8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dsu3vdfa3vz5m72rbj2xc3e0j"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-fa759e657729c2e98a32b68fb45420a8",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "eaeb4c3a-cb21-456f-9b40-390c81cbef8b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ai0dmaq8c4tpntej0ih63kf4d"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-21cc8e9abc6672a60a5eedcad444875a",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "82199bcc-1891-4a8c-bfd9-444769d49151"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2l3pvwxlbfjju6jw7ag89z79d"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-54f6ad13c3cf4d65d3c77af202f5f8db",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "680beb84-8d4b-4b9d-8260-e28b2cee0eb8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "55u0m98l7mll5xpj2zmyqwmcy"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-fa759e657729c2e98a32b68fb45420a8",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "eaeb4c3a-cb21-456f-9b40-390c81cbef8b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "er3hkstt7c3anae2nx0aftw5x"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-54f6ad13c3cf4d65d3c77af202f5f8db",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "680beb84-8d4b-4b9d-8260-e28b2cee0eb8"
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
            "value" : "96"
          }, {
            "name" : "role_jceks_password",
            "value" : "bd058bzdzm9beg8n0wqe5ynm9"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-fa759e657729c2e98a32b68fb45420a8",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "eaeb4c3a-cb21-456f-9b40-390c81cbef8b"
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
            "value" : "76"
          }, {
            "name" : "role_jceks_password",
            "value" : "4hpqgt8a6q079hjo3mwsgcdww"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "16"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "3"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/data/disk0/yarn/nm,/data/disk1/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/data/disk0/yarn/container-logs,/data/disk1/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "10350"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "17006"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "6"
          } ]
        } ],
        "items" : [ {
          "name" : "hadoop_secure_web_ui",
          "value" : "true"
        }, {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "80"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "tvIbTiiywYQ7Iw3nkpkVB2ehrU0NKu"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-d68202787ca4addfa2b7296896a014a4",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "fbdc75d3-ee6a-49b4-aa6f-d5c9b12cac26"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "32zl8y97md7hk5jgq970khe6a"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-21cc8e9abc6672a60a5eedcad444875a",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "82199bcc-1891-4a8c-bfd9-444769d49151"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5t8cu4lg7he006lk2m88ukxkq"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-321c76da0c8f8ff09f458699ad2b212f",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "bcea8950-6ce9-4d99-9c3b-7ed35b9be24b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2nrno6v2qa8yqd8a287iwcs3x"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-d68202787ca4addfa2b7296896a014a4",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "fbdc75d3-ee6a-49b4-aa6f-d5c9b12cac26"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4phw7xszd4913k6e8znp4f5ns"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-fa759e657729c2e98a32b68fb45420a8",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "eaeb4c3a-cb21-456f-9b40-390c81cbef8b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "epa7lq9bzx3c157g70ynaiym8"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-54f6ad13c3cf4d65d3c77af202f5f8db",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "680beb84-8d4b-4b9d-8260-e28b2cee0eb8"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "83"
          }, {
            "name" : "role_jceks_password",
            "value" : "cw5xsbrp2xrw028zf98sfyoxs"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "3801088000"
          }, {
            "name" : "hive_metastore_server_max_message_size",
            "value" : "380108800"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_enable_impersonation",
            "value" : "false"
          }, {
            "name" : "hiveserver2_java_heapsize",
            "value" : "3801088000"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "2099878297"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "353"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "elephant"
        }, {
          "name" : "hive_metastore_database_name",
          "value" : "hive"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive_password"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "sentry_service",
          "value" : "sentry"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-21cc8e9abc6672a60a5eedcad444875a",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "82199bcc-1891-4a8c-bfd9-444769d49151"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-321c76da0c8f8ff09f458699ad2b212f",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "bcea8950-6ce9-4d99-9c3b-7ed35b9be24b"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-54f6ad13c3cf4d65d3c77af202f5f8db",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "680beb84-8d4b-4b9d-8260-e28b2cee0eb8"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-d68202787ca4addfa2b7296896a014a4",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "fbdc75d3-ee6a-49b4-aa6f-d5c9b12cac26"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-fa759e657729c2e98a32b68fb45420a8",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "eaeb4c3a-cb21-456f-9b40-390c81cbef8b"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-21cc8e9abc6672a60a5eedcad444875a",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "82199bcc-1891-4a8c-bfd9-444769d49151"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "951uy1khl0vik5hg3lo6ssigb"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-21cc8e9abc6672a60a5eedcad444875a",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "82199bcc-1891-4a8c-bfd9-444769d49151"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "anmwizleje25gz0rp1ulbllx6"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "sentry",
      "type" : "SENTRY",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "sentry_server_database_host",
          "value" : "elephant"
        }, {
          "name" : "sentry_server_database_password",
          "value" : "sentry_password"
        }, {
          "name" : "sentry_service_admin_group",
          "value" : "hive,impala,hue,solr,kafka,hadoop,test"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "sentry-GATEWAY-21cc8e9abc6672a60a5eedcad444875a",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "82199bcc-1891-4a8c-bfd9-444769d49151"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "sentry-GATEWAY-321c76da0c8f8ff09f458699ad2b212f",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "bcea8950-6ce9-4d99-9c3b-7ed35b9be24b"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "sentry-GATEWAY-d68202787ca4addfa2b7296896a014a4",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "fbdc75d3-ee6a-49b4-aa6f-d5c9b12cac26"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "sentry-GATEWAY-fa759e657729c2e98a32b68fb45420a8",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "eaeb4c3a-cb21-456f-9b40-390c81cbef8b"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "sentry-SENTRY_SERVER-54f6ad13c3cf4d65d3c77af202f5f8db",
        "type" : "SENTRY_SERVER",
        "hostRef" : {
          "hostId" : "680beb84-8d4b-4b9d-8260-e28b2cee0eb8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "363zncb4knxyk175t1h2h9jya"
          } ]
        }
      } ],
      "displayName" : "Sentry"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "680beb84-8d4b-4b9d-8260-e28b2cee0eb8",
    "ipAddress" : "172.31.37.197",
    "hostname" : "elephant",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "eaeb4c3a-cb21-456f-9b40-390c81cbef8b",
    "ipAddress" : "172.31.46.216",
    "hostname" : "horse",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "82199bcc-1891-4a8c-bfd9-444769d49151",
    "ipAddress" : "172.31.35.136",
    "hostname" : "lion",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "bcea8950-6ce9-4d99-9c3b-7ed35b9be24b",
    "ipAddress" : "172.31.45.253",
    "hostname" : "monkey",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "fbdc75d3-ee6a-49b4-aa6f-d5c9b12cac26",
    "ipAddress" : "172.31.33.162",
    "hostname" : "tiger",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__9e00c092-4404-47ab-baa1-dc36d7f722bc",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "a47662b9f62620c5459121df03331be894694aaa2ffbbf1d9cc9b5a04124af4f",
    "pwSalt" : 8659517894739929173,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__hue-HUE_SERVER-321c76da0c8f8ff09f458699ad2b212f",
    "roles" : [ "ROLE_NAVIGATOR_ADMIN" ],
    "pwHash" : "e41fa67b0265f7459fcdaeba7a3c7d72e3974472f9007283f988951825d23ec5",
    "pwSalt" : 4434623949595842336,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__hue-HUE_SERVER-fa759e657729c2e98a32b68fb45420a8",
    "roles" : [ "ROLE_NAVIGATOR_ADMIN" ],
    "pwHash" : "c0ac381799327cf1c8c3e43338ef2d3bce8459965a2d0b26307e98afab4b561b",
    "pwSalt" : -4728393114814264944,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-ACTIVITYMONITOR-54f6ad13c3cf4d65d3c77af202f5f8db",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "2d489c195cb31f47cc8e32750fef6c1af0d915b98c5c4576f5703452bd171d2c",
    "pwSalt" : -4405905643540883876,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-54f6ad13c3cf4d65d3c77af202f5f8db",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "7b886c31eb63715b6b64c3807bc1efa962b405028cccd11de16a60e3368fa821",
    "pwSalt" : -6114409571482662727,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-54f6ad13c3cf4d65d3c77af202f5f8db",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "0233048f1e8957d3a1df8687a59845504096e5ceb629f5e530438847f568f094",
    "pwSalt" : -4820852464988278512,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-54f6ad13c3cf4d65d3c77af202f5f8db",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "46419ff33ab8ab3fe26af4f034a6f910766842e89a5f31def62e7a5ad5ee9d00",
    "pwSalt" : 1338645503448744562,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-54f6ad13c3cf4d65d3c77af202f5f8db",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "6b41d4fc26953cf228da485431e497666d3f80c6b8d4da5666a29811979d6f29",
    "pwSalt" : 1697191985398736812,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "2448774729f69fb3dd0b1eb5d6302035aad7fadc767cef5a4ec67f0a00db0e5d",
    "pwSalt" : -4158019105405643577,
    "pwLogin" : true
  }, {
    "name" : "ahuertaf",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "bffd81fec77adef19cd268d2f6c1517cba81ff38fe507d84dee88ba73b500717",
    "pwSalt" : 3644954688706357681,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "c05b843a08b9c3b10df400810c0dd05dd9b9a2b0169ed2d0735cbbe4b3281366",
    "pwSalt" : -7144455528167353928,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.12.1",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20170818-0807",
    "gitHash" : "9bdee611802535491d400e03c98ef694a2c77d0a",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "ACTIVITYMONITOR",
        "items" : [ {
          "name" : "firehose_database_host",
          "value" : "elephant"
        }, {
          "name" : "firehose_database_name",
          "value" : "amon"
        }, {
          "name" : "firehose_database_password",
          "value" : "amon_password"
        }, {
          "name" : "firehose_database_user",
          "value" : "amon"
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
          "value" : "elephant"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman_password"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
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
      "name" : "mgmt-ACTIVITYMONITOR-54f6ad13c3cf4d65d3c77af202f5f8db",
      "type" : "ACTIVITYMONITOR",
      "hostRef" : {
        "hostId" : "680beb84-8d4b-4b9d-8260-e28b2cee0eb8"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "88v5t68cl3m74yg0rz4jyeoq"
        } ]
      }
    }, {
      "name" : "mgmt-ALERTPUBLISHER-54f6ad13c3cf4d65d3c77af202f5f8db",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "680beb84-8d4b-4b9d-8260-e28b2cee0eb8"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "bmk21asnyjjep0vx84v3n3wfr"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-54f6ad13c3cf4d65d3c77af202f5f8db",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "680beb84-8d4b-4b9d-8260-e28b2cee0eb8"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "5prz8eqgqtxev7g72i04qro6m"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-54f6ad13c3cf4d65d3c77af202f5f8db",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "680beb84-8d4b-4b9d-8260-e28b2cee0eb8"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "f30gz4oiyw2i1o4ia4bforaiv"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-54f6ad13c3cf4d65d3c77af202f5f8db",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "680beb84-8d4b-4b9d-8260-e28b2cee0eb8"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "e981d0sjuqobb47dejiaa7ydp"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-54f6ad13c3cf4d65d3c77af202f5f8db",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "680beb84-8d4b-4b9d-8260-e28b2cee0eb8"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "7679z1jex45zqcohbu9eaejq9"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "AD_USE_SIMPLE_AUTH",
      "value" : "false"
    }, {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/26/2012 16:40"
    }, {
      "name" : "KDC_ADMIN_HOST",
      "value" : "elephant.vinkos"
    }, {
      "name" : "KDC_ADMIN_PASSWORD",
      "value" : "BQIAAAA9AAEAClZJTktPUy5DT00ADGNsb3VkZXJhLXNjbQAAAAFaHvscAQAXABCIRvfq7o+xF60Gvdgwt1hsAAAAAQ=="
    }, {
      "name" : "KDC_ADMIN_USER",
      "value" : "cloudera-scm@VINKOS.COM"
    }, {
      "name" : "KDC_HOST",
      "value" : "elephant.vinkos"
    }, {
      "name" : "KRB_ENC_TYPES",
      "value" : "arcfour-hmac"
    }, {
      "name" : "KRB_MANAGE_KRB5_CONF",
      "value" : "true"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,http://archive.cloudera.com/kudu/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    }, {
      "name" : "SECURITY_REALM",
      "value" : "VINKOS.COM"
    } ]
  }
}
```
