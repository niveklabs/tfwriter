# kubernetes_cron_job

[back](../kubernetes.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    kubernetes = ">= 2.0.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "kubernetes_cron_job" {
  source = "./modules/kubernetes/r/kubernetes_cron_job"


  metadata = [{
    annotations      = {}
    generate_name    = null
    generation       = null
    labels           = {}
    name             = null
    namespace        = null
    resource_version = null
    self_link        = null
    uid              = null
  }]

  spec = [{
    concurrency_policy        = null
    failed_jobs_history_limit = null
    job_template = [{
      metadata = [{
        annotations      = {}
        generate_name    = null
        generation       = null
        labels           = {}
        name             = null
        resource_version = null
        self_link        = null
        uid              = null
      }]
      spec = [{
        active_deadline_seconds = null
        backoff_limit           = null
        completions             = null
        manual_selector         = null
        parallelism             = null
        selector = [{
          match_expressions = [{
            key      = null
            operator = null
            values   = []
          }]
          match_labels = {}
        }]
        template = [{
          metadata = [{
            annotations      = {}
            generate_name    = null
            generation       = null
            labels           = {}
            name             = null
            resource_version = null
            self_link        = null
            uid              = null
          }]
          spec = [{
            active_deadline_seconds = null
            affinity = [{
              node_affinity = [{
                preferred_during_scheduling_ignored_during_execution = [{
                  preference = [{
                    match_expressions = [{
                      key      = null
                      operator = null
                      values   = []
                    }]
                  }]
                  weight = null
                }]
                required_during_scheduling_ignored_during_execution = [{
                  node_selector_term = [{
                    match_expressions = [{
                      key      = null
                      operator = null
                      values   = []
                    }]
                  }]
                }]
              }]
              pod_affinity = [{
                preferred_during_scheduling_ignored_during_execution = [{
                  pod_affinity_term = [{
                    label_selector = [{
                      match_expressions = [{
                        key      = null
                        operator = null
                        values   = []
                      }]
                      match_labels = {}
                    }]
                    namespaces   = []
                    topology_key = null
                  }]
                  weight = null
                }]
                required_during_scheduling_ignored_during_execution = [{
                  label_selector = [{
                    match_expressions = [{
                      key      = null
                      operator = null
                      values   = []
                    }]
                    match_labels = {}
                  }]
                  namespaces   = []
                  topology_key = null
                }]
              }]
              pod_anti_affinity = [{
                preferred_during_scheduling_ignored_during_execution = [{
                  pod_affinity_term = [{
                    label_selector = [{
                      match_expressions = [{
                        key      = null
                        operator = null
                        values   = []
                      }]
                      match_labels = {}
                    }]
                    namespaces   = []
                    topology_key = null
                  }]
                  weight = null
                }]
                required_during_scheduling_ignored_during_execution = [{
                  label_selector = [{
                    match_expressions = [{
                      key      = null
                      operator = null
                      values   = []
                    }]
                    match_labels = {}
                  }]
                  namespaces   = []
                  topology_key = null
                }]
              }]
            }]
            automount_service_account_token = null
            container = [{
              args    = []
              command = []
              env = [{
                name  = null
                value = null
                value_from = [{
                  config_map_key_ref = [{
                    key      = null
                    name     = null
                    optional = null
                  }]
                  field_ref = [{
                    api_version = null
                    field_path  = null
                  }]
                  resource_field_ref = [{
                    container_name = null
                    divisor        = null
                    resource       = null
                  }]
                  secret_key_ref = [{
                    key      = null
                    name     = null
                    optional = null
                  }]
                }]
              }]
              env_from = [{
                config_map_ref = [{
                  name     = null
                  optional = null
                }]
                prefix = null
                secret_ref = [{
                  name     = null
                  optional = null
                }]
              }]
              image             = null
              image_pull_policy = null
              lifecycle = [{
                post_start = [{
                  exec = [{
                    command = []
                  }]
                  http_get = [{
                    host = null
                    http_header = [{
                      name  = null
                      value = null
                    }]
                    path   = null
                    port   = null
                    scheme = null
                  }]
                  tcp_socket = [{
                    port = null
                  }]
                }]
                pre_stop = [{
                  exec = [{
                    command = []
                  }]
                  http_get = [{
                    host = null
                    http_header = [{
                      name  = null
                      value = null
                    }]
                    path   = null
                    port   = null
                    scheme = null
                  }]
                  tcp_socket = [{
                    port = null
                  }]
                }]
              }]
              liveness_probe = [{
                exec = [{
                  command = []
                }]
                failure_threshold = null
                http_get = [{
                  host = null
                  http_header = [{
                    name  = null
                    value = null
                  }]
                  path   = null
                  port   = null
                  scheme = null
                }]
                initial_delay_seconds = null
                period_seconds        = null
                success_threshold     = null
                tcp_socket = [{
                  port = null
                }]
                timeout_seconds = null
              }]
              name = null
              port = [{
                container_port = null
                host_ip        = null
                host_port      = null
                name           = null
                protocol       = null
              }]
              readiness_probe = [{
                exec = [{
                  command = []
                }]
                failure_threshold = null
                http_get = [{
                  host = null
                  http_header = [{
                    name  = null
                    value = null
                  }]
                  path   = null
                  port   = null
                  scheme = null
                }]
                initial_delay_seconds = null
                period_seconds        = null
                success_threshold     = null
                tcp_socket = [{
                  port = null
                }]
                timeout_seconds = null
              }]
              resources = [{
                limits   = {}
                requests = {}
              }]
              security_context = [{
                allow_privilege_escalation = null
                capabilities = [{
                  add  = []
                  drop = []
                }]
                privileged                = null
                read_only_root_filesystem = null
                run_as_group              = null
                run_as_non_root           = null
                run_as_user               = null
                se_linux_options = [{
                  level = null
                  role  = null
                  type  = null
                  user  = null
                }]
              }]
              startup_probe = [{
                exec = [{
                  command = []
                }]
                failure_threshold = null
                http_get = [{
                  host = null
                  http_header = [{
                    name  = null
                    value = null
                  }]
                  path   = null
                  port   = null
                  scheme = null
                }]
                initial_delay_seconds = null
                period_seconds        = null
                success_threshold     = null
                tcp_socket = [{
                  port = null
                }]
                timeout_seconds = null
              }]
              stdin                      = null
              stdin_once                 = null
              termination_message_path   = null
              termination_message_policy = null
              tty                        = null
              volume_mount = [{
                mount_path        = null
                mount_propagation = null
                name              = null
                read_only         = null
                sub_path          = null
              }]
              working_dir = null
            }]
            dns_config = [{
              nameservers = []
              option = [{
                name  = null
                value = null
              }]
              searches = []
            }]
            dns_policy           = null
            enable_service_links = null
            host_aliases = [{
              hostnames = []
              ip        = null
            }]
            host_ipc     = null
            host_network = null
            host_pid     = null
            hostname     = null
            image_pull_secrets = [{
              name = null
            }]
            init_container = [{
              args    = []
              command = []
              env = [{
                name  = null
                value = null
                value_from = [{
                  config_map_key_ref = [{
                    key      = null
                    name     = null
                    optional = null
                  }]
                  field_ref = [{
                    api_version = null
                    field_path  = null
                  }]
                  resource_field_ref = [{
                    container_name = null
                    divisor        = null
                    resource       = null
                  }]
                  secret_key_ref = [{
                    key      = null
                    name     = null
                    optional = null
                  }]
                }]
              }]
              env_from = [{
                config_map_ref = [{
                  name     = null
                  optional = null
                }]
                prefix = null
                secret_ref = [{
                  name     = null
                  optional = null
                }]
              }]
              image             = null
              image_pull_policy = null
              lifecycle = [{
                post_start = [{
                  exec = [{
                    command = []
                  }]
                  http_get = [{
                    host = null
                    http_header = [{
                      name  = null
                      value = null
                    }]
                    path   = null
                    port   = null
                    scheme = null
                  }]
                  tcp_socket = [{
                    port = null
                  }]
                }]
                pre_stop = [{
                  exec = [{
                    command = []
                  }]
                  http_get = [{
                    host = null
                    http_header = [{
                      name  = null
                      value = null
                    }]
                    path   = null
                    port   = null
                    scheme = null
                  }]
                  tcp_socket = [{
                    port = null
                  }]
                }]
              }]
              liveness_probe = [{
                exec = [{
                  command = []
                }]
                failure_threshold = null
                http_get = [{
                  host = null
                  http_header = [{
                    name  = null
                    value = null
                  }]
                  path   = null
                  port   = null
                  scheme = null
                }]
                initial_delay_seconds = null
                period_seconds        = null
                success_threshold     = null
                tcp_socket = [{
                  port = null
                }]
                timeout_seconds = null
              }]
              name = null
              port = [{
                container_port = null
                host_ip        = null
                host_port      = null
                name           = null
                protocol       = null
              }]
              readiness_probe = [{
                exec = [{
                  command = []
                }]
                failure_threshold = null
                http_get = [{
                  host = null
                  http_header = [{
                    name  = null
                    value = null
                  }]
                  path   = null
                  port   = null
                  scheme = null
                }]
                initial_delay_seconds = null
                period_seconds        = null
                success_threshold     = null
                tcp_socket = [{
                  port = null
                }]
                timeout_seconds = null
              }]
              resources = [{
                limits   = {}
                requests = {}
              }]
              security_context = [{
                allow_privilege_escalation = null
                capabilities = [{
                  add  = []
                  drop = []
                }]
                privileged                = null
                read_only_root_filesystem = null
                run_as_group              = null
                run_as_non_root           = null
                run_as_user               = null
                se_linux_options = [{
                  level = null
                  role  = null
                  type  = null
                  user  = null
                }]
              }]
              startup_probe = [{
                exec = [{
                  command = []
                }]
                failure_threshold = null
                http_get = [{
                  host = null
                  http_header = [{
                    name  = null
                    value = null
                  }]
                  path   = null
                  port   = null
                  scheme = null
                }]
                initial_delay_seconds = null
                period_seconds        = null
                success_threshold     = null
                tcp_socket = [{
                  port = null
                }]
                timeout_seconds = null
              }]
              stdin                      = null
              stdin_once                 = null
              termination_message_path   = null
              termination_message_policy = null
              tty                        = null
              volume_mount = [{
                mount_path        = null
                mount_propagation = null
                name              = null
                read_only         = null
                sub_path          = null
              }]
              working_dir = null
            }]
            node_name           = null
            node_selector       = {}
            priority_class_name = null
            readiness_gate = [{
              condition_type = null
            }]
            restart_policy = null
            security_context = [{
              fs_group        = null
              run_as_group    = null
              run_as_non_root = null
              run_as_user     = null
              se_linux_options = [{
                level = null
                role  = null
                type  = null
                user  = null
              }]
              supplemental_groups = []
              sysctl = [{
                name  = null
                value = null
              }]
            }]
            service_account_name             = null
            share_process_namespace          = null
            subdomain                        = null
            termination_grace_period_seconds = null
            toleration = [{
              effect             = null
              key                = null
              operator           = null
              toleration_seconds = null
              value              = null
            }]
            topology_spread_constraint = [{
              label_selector = [{
                match_expressions = [{
                  key      = null
                  operator = null
                  values   = []
                }]
                match_labels = {}
              }]
              max_skew           = null
              topology_key       = null
              when_unsatisfiable = null
            }]
            volume = [{
              aws_elastic_block_store = [{
                fs_type   = null
                partition = null
                read_only = null
                volume_id = null
              }]
              azure_disk = [{
                caching_mode  = null
                data_disk_uri = null
                disk_name     = null
                fs_type       = null
                kind          = null
                read_only     = null
              }]
              azure_file = [{
                read_only   = null
                secret_name = null
                share_name  = null
              }]
              ceph_fs = [{
                monitors    = []
                path        = null
                read_only   = null
                secret_file = null
                secret_ref = [{
                  name      = null
                  namespace = null
                }]
                user = null
              }]
              cinder = [{
                fs_type   = null
                read_only = null
                volume_id = null
              }]
              config_map = [{
                default_mode = null
                items = [{
                  key  = null
                  mode = null
                  path = null
                }]
                name     = null
                optional = null
              }]
              csi = [{
                controller_expand_secret_ref = [{
                  name      = null
                  namespace = null
                }]
                controller_publish_secret_ref = [{
                  name      = null
                  namespace = null
                }]
                driver  = null
                fs_type = null
                node_publish_secret_ref = [{
                  name      = null
                  namespace = null
                }]
                node_stage_secret_ref = [{
                  name      = null
                  namespace = null
                }]
                read_only         = null
                volume_attributes = {}
                volume_handle     = null
              }]
              downward_api = [{
                default_mode = null
                items = [{
                  field_ref = [{
                    api_version = null
                    field_path  = null
                  }]
                  mode = null
                  path = null
                  resource_field_ref = [{
                    container_name = null
                    divisor        = null
                    resource       = null
                  }]
                }]
              }]
              empty_dir = [{
                medium     = null
                size_limit = null
              }]
              fc = [{
                fs_type      = null
                lun          = null
                read_only    = null
                target_ww_ns = []
              }]
              flex_volume = [{
                driver    = null
                fs_type   = null
                options   = {}
                read_only = null
                secret_ref = [{
                  name      = null
                  namespace = null
                }]
              }]
              flocker = [{
                dataset_name = null
                dataset_uuid = null
              }]
              gce_persistent_disk = [{
                fs_type   = null
                partition = null
                pd_name   = null
                read_only = null
              }]
              git_repo = [{
                directory  = null
                repository = null
                revision   = null
              }]
              glusterfs = [{
                endpoints_name = null
                path           = null
                read_only      = null
              }]
              host_path = [{
                path = null
                type = null
              }]
              iscsi = [{
                fs_type         = null
                iqn             = null
                iscsi_interface = null
                lun             = null
                read_only       = null
                target_portal   = null
              }]
              local = [{
                path = null
              }]
              name = null
              nfs = [{
                path      = null
                read_only = null
                server    = null
              }]
              persistent_volume_claim = [{
                claim_name = null
                read_only  = null
              }]
              photon_persistent_disk = [{
                fs_type = null
                pd_id   = null
              }]
              projected = [{
                default_mode = null
                sources = [{
                  config_map = [{
                    items = [{
                      key  = null
                      mode = null
                      path = null
                    }]
                    name     = null
                    optional = null
                  }]
                  downward_api = [{
                    items = [{
                      field_ref = [{
                        api_version = null
                        field_path  = null
                      }]
                      mode = null
                      path = null
                      resource_field_ref = [{
                        container_name = null
                        divisor        = null
                        resource       = null
                      }]
                    }]
                  }]
                  secret = [{
                    items = [{
                      key  = null
                      mode = null
                      path = null
                    }]
                    name     = null
                    optional = null
                  }]
                  service_account_token = [{
                    audience           = null
                    expiration_seconds = null
                    path               = null
                  }]
                }]
              }]
              quobyte = [{
                group     = null
                read_only = null
                registry  = null
                user      = null
                volume    = null
              }]
              rbd = [{
                ceph_monitors = []
                fs_type       = null
                keyring       = null
                rados_user    = null
                rbd_image     = null
                rbd_pool      = null
                read_only     = null
                secret_ref = [{
                  name      = null
                  namespace = null
                }]
              }]
              secret = [{
                default_mode = null
                items = [{
                  key  = null
                  mode = null
                  path = null
                }]
                optional    = null
                secret_name = null
              }]
              vsphere_volume = [{
                fs_type     = null
                volume_path = null
              }]
            }]
          }]
        }]
        ttl_seconds_after_finished = null
      }]
    }]
    schedule                      = null
    starting_deadline_seconds     = null
    successful_jobs_history_limit = null
    suspend                       = null
  }]

  timeouts = [{
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "metadata" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      annotations      = map(string)
      generate_name    = string
      generation       = number
      labels           = map(string)
      name             = string
      namespace        = string
      resource_version = string
      self_link        = string
      uid              = string
    }
  ))
}

variable "spec" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      concurrency_policy        = string
      failed_jobs_history_limit = number
      job_template = list(object(
        {
          metadata = list(object(
            {
              annotations      = map(string)
              generate_name    = string
              generation       = number
              labels           = map(string)
              name             = string
              resource_version = string
              self_link        = string
              uid              = string
            }
          ))
          spec = list(object(
            {
              active_deadline_seconds = number
              backoff_limit           = number
              completions             = number
              manual_selector         = bool
              parallelism             = number
              selector = list(object(
                {
                  match_expressions = list(object(
                    {
                      key      = string
                      operator = string
                      values   = set(string)
                    }
                  ))
                  match_labels = map(string)
                }
              ))
              template = list(object(
                {
                  metadata = list(object(
                    {
                      annotations      = map(string)
                      generate_name    = string
                      generation       = number
                      labels           = map(string)
                      name             = string
                      resource_version = string
                      self_link        = string
                      uid              = string
                    }
                  ))
                  spec = list(object(
                    {
                      active_deadline_seconds = number
                      affinity = list(object(
                        {
                          node_affinity = list(object(
                            {
                              preferred_during_scheduling_ignored_during_execution = list(object(
                                {
                                  preference = list(object(
                                    {
                                      match_expressions = list(object(
                                        {
                                          key      = string
                                          operator = string
                                          values   = set(string)
                                        }
                                      ))
                                    }
                                  ))
                                  weight = number
                                }
                              ))
                              required_during_scheduling_ignored_during_execution = list(object(
                                {
                                  node_selector_term = list(object(
                                    {
                                      match_expressions = list(object(
                                        {
                                          key      = string
                                          operator = string
                                          values   = set(string)
                                        }
                                      ))
                                    }
                                  ))
                                }
                              ))
                            }
                          ))
                          pod_affinity = list(object(
                            {
                              preferred_during_scheduling_ignored_during_execution = list(object(
                                {
                                  pod_affinity_term = list(object(
                                    {
                                      label_selector = list(object(
                                        {
                                          match_expressions = list(object(
                                            {
                                              key      = string
                                              operator = string
                                              values   = set(string)
                                            }
                                          ))
                                          match_labels = map(string)
                                        }
                                      ))
                                      namespaces   = set(string)
                                      topology_key = string
                                    }
                                  ))
                                  weight = number
                                }
                              ))
                              required_during_scheduling_ignored_during_execution = list(object(
                                {
                                  label_selector = list(object(
                                    {
                                      match_expressions = list(object(
                                        {
                                          key      = string
                                          operator = string
                                          values   = set(string)
                                        }
                                      ))
                                      match_labels = map(string)
                                    }
                                  ))
                                  namespaces   = set(string)
                                  topology_key = string
                                }
                              ))
                            }
                          ))
                          pod_anti_affinity = list(object(
                            {
                              preferred_during_scheduling_ignored_during_execution = list(object(
                                {
                                  pod_affinity_term = list(object(
                                    {
                                      label_selector = list(object(
                                        {
                                          match_expressions = list(object(
                                            {
                                              key      = string
                                              operator = string
                                              values   = set(string)
                                            }
                                          ))
                                          match_labels = map(string)
                                        }
                                      ))
                                      namespaces   = set(string)
                                      topology_key = string
                                    }
                                  ))
                                  weight = number
                                }
                              ))
                              required_during_scheduling_ignored_during_execution = list(object(
                                {
                                  label_selector = list(object(
                                    {
                                      match_expressions = list(object(
                                        {
                                          key      = string
                                          operator = string
                                          values   = set(string)
                                        }
                                      ))
                                      match_labels = map(string)
                                    }
                                  ))
                                  namespaces   = set(string)
                                  topology_key = string
                                }
                              ))
                            }
                          ))
                        }
                      ))
                      automount_service_account_token = bool
                      container = list(object(
                        {
                          args    = list(string)
                          command = list(string)
                          env = list(object(
                            {
                              name  = string
                              value = string
                              value_from = list(object(
                                {
                                  config_map_key_ref = list(object(
                                    {
                                      key      = string
                                      name     = string
                                      optional = bool
                                    }
                                  ))
                                  field_ref = list(object(
                                    {
                                      api_version = string
                                      field_path  = string
                                    }
                                  ))
                                  resource_field_ref = list(object(
                                    {
                                      container_name = string
                                      divisor        = string
                                      resource       = string
                                    }
                                  ))
                                  secret_key_ref = list(object(
                                    {
                                      key      = string
                                      name     = string
                                      optional = bool
                                    }
                                  ))
                                }
                              ))
                            }
                          ))
                          env_from = list(object(
                            {
                              config_map_ref = list(object(
                                {
                                  name     = string
                                  optional = bool
                                }
                              ))
                              prefix = string
                              secret_ref = list(object(
                                {
                                  name     = string
                                  optional = bool
                                }
                              ))
                            }
                          ))
                          image             = string
                          image_pull_policy = string
                          lifecycle = list(object(
                            {
                              post_start = list(object(
                                {
                                  exec = list(object(
                                    {
                                      command = list(string)
                                    }
                                  ))
                                  http_get = list(object(
                                    {
                                      host = string
                                      http_header = list(object(
                                        {
                                          name  = string
                                          value = string
                                        }
                                      ))
                                      path   = string
                                      port   = string
                                      scheme = string
                                    }
                                  ))
                                  tcp_socket = list(object(
                                    {
                                      port = string
                                    }
                                  ))
                                }
                              ))
                              pre_stop = list(object(
                                {
                                  exec = list(object(
                                    {
                                      command = list(string)
                                    }
                                  ))
                                  http_get = list(object(
                                    {
                                      host = string
                                      http_header = list(object(
                                        {
                                          name  = string
                                          value = string
                                        }
                                      ))
                                      path   = string
                                      port   = string
                                      scheme = string
                                    }
                                  ))
                                  tcp_socket = list(object(
                                    {
                                      port = string
                                    }
                                  ))
                                }
                              ))
                            }
                          ))
                          liveness_probe = list(object(
                            {
                              exec = list(object(
                                {
                                  command = list(string)
                                }
                              ))
                              failure_threshold = number
                              http_get = list(object(
                                {
                                  host = string
                                  http_header = list(object(
                                    {
                                      name  = string
                                      value = string
                                    }
                                  ))
                                  path   = string
                                  port   = string
                                  scheme = string
                                }
                              ))
                              initial_delay_seconds = number
                              period_seconds        = number
                              success_threshold     = number
                              tcp_socket = list(object(
                                {
                                  port = string
                                }
                              ))
                              timeout_seconds = number
                            }
                          ))
                          name = string
                          port = list(object(
                            {
                              container_port = number
                              host_ip        = string
                              host_port      = number
                              name           = string
                              protocol       = string
                            }
                          ))
                          readiness_probe = list(object(
                            {
                              exec = list(object(
                                {
                                  command = list(string)
                                }
                              ))
                              failure_threshold = number
                              http_get = list(object(
                                {
                                  host = string
                                  http_header = list(object(
                                    {
                                      name  = string
                                      value = string
                                    }
                                  ))
                                  path   = string
                                  port   = string
                                  scheme = string
                                }
                              ))
                              initial_delay_seconds = number
                              period_seconds        = number
                              success_threshold     = number
                              tcp_socket = list(object(
                                {
                                  port = string
                                }
                              ))
                              timeout_seconds = number
                            }
                          ))
                          resources = list(object(
                            {
                              limits   = map(string)
                              requests = map(string)
                            }
                          ))
                          security_context = list(object(
                            {
                              allow_privilege_escalation = bool
                              capabilities = list(object(
                                {
                                  add  = list(string)
                                  drop = list(string)
                                }
                              ))
                              privileged                = bool
                              read_only_root_filesystem = bool
                              run_as_group              = string
                              run_as_non_root           = bool
                              run_as_user               = string
                              se_linux_options = list(object(
                                {
                                  level = string
                                  role  = string
                                  type  = string
                                  user  = string
                                }
                              ))
                            }
                          ))
                          startup_probe = list(object(
                            {
                              exec = list(object(
                                {
                                  command = list(string)
                                }
                              ))
                              failure_threshold = number
                              http_get = list(object(
                                {
                                  host = string
                                  http_header = list(object(
                                    {
                                      name  = string
                                      value = string
                                    }
                                  ))
                                  path   = string
                                  port   = string
                                  scheme = string
                                }
                              ))
                              initial_delay_seconds = number
                              period_seconds        = number
                              success_threshold     = number
                              tcp_socket = list(object(
                                {
                                  port = string
                                }
                              ))
                              timeout_seconds = number
                            }
                          ))
                          stdin                      = bool
                          stdin_once                 = bool
                          termination_message_path   = string
                          termination_message_policy = string
                          tty                        = bool
                          volume_mount = list(object(
                            {
                              mount_path        = string
                              mount_propagation = string
                              name              = string
                              read_only         = bool
                              sub_path          = string
                            }
                          ))
                          working_dir = string
                        }
                      ))
                      dns_config = list(object(
                        {
                          nameservers = list(string)
                          option = list(object(
                            {
                              name  = string
                              value = string
                            }
                          ))
                          searches = list(string)
                        }
                      ))
                      dns_policy           = string
                      enable_service_links = bool
                      host_aliases = list(object(
                        {
                          hostnames = list(string)
                          ip        = string
                        }
                      ))
                      host_ipc     = bool
                      host_network = bool
                      host_pid     = bool
                      hostname     = string
                      image_pull_secrets = list(object(
                        {
                          name = string
                        }
                      ))
                      init_container = list(object(
                        {
                          args    = list(string)
                          command = list(string)
                          env = list(object(
                            {
                              name  = string
                              value = string
                              value_from = list(object(
                                {
                                  config_map_key_ref = list(object(
                                    {
                                      key      = string
                                      name     = string
                                      optional = bool
                                    }
                                  ))
                                  field_ref = list(object(
                                    {
                                      api_version = string
                                      field_path  = string
                                    }
                                  ))
                                  resource_field_ref = list(object(
                                    {
                                      container_name = string
                                      divisor        = string
                                      resource       = string
                                    }
                                  ))
                                  secret_key_ref = list(object(
                                    {
                                      key      = string
                                      name     = string
                                      optional = bool
                                    }
                                  ))
                                }
                              ))
                            }
                          ))
                          env_from = list(object(
                            {
                              config_map_ref = list(object(
                                {
                                  name     = string
                                  optional = bool
                                }
                              ))
                              prefix = string
                              secret_ref = list(object(
                                {
                                  name     = string
                                  optional = bool
                                }
                              ))
                            }
                          ))
                          image             = string
                          image_pull_policy = string
                          lifecycle = list(object(
                            {
                              post_start = list(object(
                                {
                                  exec = list(object(
                                    {
                                      command = list(string)
                                    }
                                  ))
                                  http_get = list(object(
                                    {
                                      host = string
                                      http_header = list(object(
                                        {
                                          name  = string
                                          value = string
                                        }
                                      ))
                                      path   = string
                                      port   = string
                                      scheme = string
                                    }
                                  ))
                                  tcp_socket = list(object(
                                    {
                                      port = string
                                    }
                                  ))
                                }
                              ))
                              pre_stop = list(object(
                                {
                                  exec = list(object(
                                    {
                                      command = list(string)
                                    }
                                  ))
                                  http_get = list(object(
                                    {
                                      host = string
                                      http_header = list(object(
                                        {
                                          name  = string
                                          value = string
                                        }
                                      ))
                                      path   = string
                                      port   = string
                                      scheme = string
                                    }
                                  ))
                                  tcp_socket = list(object(
                                    {
                                      port = string
                                    }
                                  ))
                                }
                              ))
                            }
                          ))
                          liveness_probe = list(object(
                            {
                              exec = list(object(
                                {
                                  command = list(string)
                                }
                              ))
                              failure_threshold = number
                              http_get = list(object(
                                {
                                  host = string
                                  http_header = list(object(
                                    {
                                      name  = string
                                      value = string
                                    }
                                  ))
                                  path   = string
                                  port   = string
                                  scheme = string
                                }
                              ))
                              initial_delay_seconds = number
                              period_seconds        = number
                              success_threshold     = number
                              tcp_socket = list(object(
                                {
                                  port = string
                                }
                              ))
                              timeout_seconds = number
                            }
                          ))
                          name = string
                          port = list(object(
                            {
                              container_port = number
                              host_ip        = string
                              host_port      = number
                              name           = string
                              protocol       = string
                            }
                          ))
                          readiness_probe = list(object(
                            {
                              exec = list(object(
                                {
                                  command = list(string)
                                }
                              ))
                              failure_threshold = number
                              http_get = list(object(
                                {
                                  host = string
                                  http_header = list(object(
                                    {
                                      name  = string
                                      value = string
                                    }
                                  ))
                                  path   = string
                                  port   = string
                                  scheme = string
                                }
                              ))
                              initial_delay_seconds = number
                              period_seconds        = number
                              success_threshold     = number
                              tcp_socket = list(object(
                                {
                                  port = string
                                }
                              ))
                              timeout_seconds = number
                            }
                          ))
                          resources = list(object(
                            {
                              limits   = map(string)
                              requests = map(string)
                            }
                          ))
                          security_context = list(object(
                            {
                              allow_privilege_escalation = bool
                              capabilities = list(object(
                                {
                                  add  = list(string)
                                  drop = list(string)
                                }
                              ))
                              privileged                = bool
                              read_only_root_filesystem = bool
                              run_as_group              = string
                              run_as_non_root           = bool
                              run_as_user               = string
                              se_linux_options = list(object(
                                {
                                  level = string
                                  role  = string
                                  type  = string
                                  user  = string
                                }
                              ))
                            }
                          ))
                          startup_probe = list(object(
                            {
                              exec = list(object(
                                {
                                  command = list(string)
                                }
                              ))
                              failure_threshold = number
                              http_get = list(object(
                                {
                                  host = string
                                  http_header = list(object(
                                    {
                                      name  = string
                                      value = string
                                    }
                                  ))
                                  path   = string
                                  port   = string
                                  scheme = string
                                }
                              ))
                              initial_delay_seconds = number
                              period_seconds        = number
                              success_threshold     = number
                              tcp_socket = list(object(
                                {
                                  port = string
                                }
                              ))
                              timeout_seconds = number
                            }
                          ))
                          stdin                      = bool
                          stdin_once                 = bool
                          termination_message_path   = string
                          termination_message_policy = string
                          tty                        = bool
                          volume_mount = list(object(
                            {
                              mount_path        = string
                              mount_propagation = string
                              name              = string
                              read_only         = bool
                              sub_path          = string
                            }
                          ))
                          working_dir = string
                        }
                      ))
                      node_name           = string
                      node_selector       = map(string)
                      priority_class_name = string
                      readiness_gate = list(object(
                        {
                          condition_type = string
                        }
                      ))
                      restart_policy = string
                      security_context = list(object(
                        {
                          fs_group        = string
                          run_as_group    = string
                          run_as_non_root = bool
                          run_as_user     = string
                          se_linux_options = list(object(
                            {
                              level = string
                              role  = string
                              type  = string
                              user  = string
                            }
                          ))
                          supplemental_groups = set(number)
                          sysctl = list(object(
                            {
                              name  = string
                              value = string
                            }
                          ))
                        }
                      ))
                      service_account_name             = string
                      share_process_namespace          = bool
                      subdomain                        = string
                      termination_grace_period_seconds = number
                      toleration = list(object(
                        {
                          effect             = string
                          key                = string
                          operator           = string
                          toleration_seconds = string
                          value              = string
                        }
                      ))
                      topology_spread_constraint = list(object(
                        {
                          label_selector = list(object(
                            {
                              match_expressions = list(object(
                                {
                                  key      = string
                                  operator = string
                                  values   = set(string)
                                }
                              ))
                              match_labels = map(string)
                            }
                          ))
                          max_skew           = number
                          topology_key       = string
                          when_unsatisfiable = string
                        }
                      ))
                      volume = list(object(
                        {
                          aws_elastic_block_store = list(object(
                            {
                              fs_type   = string
                              partition = number
                              read_only = bool
                              volume_id = string
                            }
                          ))
                          azure_disk = list(object(
                            {
                              caching_mode  = string
                              data_disk_uri = string
                              disk_name     = string
                              fs_type       = string
                              kind          = string
                              read_only     = bool
                            }
                          ))
                          azure_file = list(object(
                            {
                              read_only   = bool
                              secret_name = string
                              share_name  = string
                            }
                          ))
                          ceph_fs = list(object(
                            {
                              monitors    = set(string)
                              path        = string
                              read_only   = bool
                              secret_file = string
                              secret_ref = list(object(
                                {
                                  name      = string
                                  namespace = string
                                }
                              ))
                              user = string
                            }
                          ))
                          cinder = list(object(
                            {
                              fs_type   = string
                              read_only = bool
                              volume_id = string
                            }
                          ))
                          config_map = list(object(
                            {
                              default_mode = string
                              items = list(object(
                                {
                                  key  = string
                                  mode = string
                                  path = string
                                }
                              ))
                              name     = string
                              optional = bool
                            }
                          ))
                          csi = list(object(
                            {
                              controller_expand_secret_ref = list(object(
                                {
                                  name      = string
                                  namespace = string
                                }
                              ))
                              controller_publish_secret_ref = list(object(
                                {
                                  name      = string
                                  namespace = string
                                }
                              ))
                              driver  = string
                              fs_type = string
                              node_publish_secret_ref = list(object(
                                {
                                  name      = string
                                  namespace = string
                                }
                              ))
                              node_stage_secret_ref = list(object(
                                {
                                  name      = string
                                  namespace = string
                                }
                              ))
                              read_only         = bool
                              volume_attributes = map(string)
                              volume_handle     = string
                            }
                          ))
                          downward_api = list(object(
                            {
                              default_mode = string
                              items = list(object(
                                {
                                  field_ref = list(object(
                                    {
                                      api_version = string
                                      field_path  = string
                                    }
                                  ))
                                  mode = string
                                  path = string
                                  resource_field_ref = list(object(
                                    {
                                      container_name = string
                                      divisor        = string
                                      resource       = string
                                    }
                                  ))
                                }
                              ))
                            }
                          ))
                          empty_dir = list(object(
                            {
                              medium     = string
                              size_limit = string
                            }
                          ))
                          fc = list(object(
                            {
                              fs_type      = string
                              lun          = number
                              read_only    = bool
                              target_ww_ns = set(string)
                            }
                          ))
                          flex_volume = list(object(
                            {
                              driver    = string
                              fs_type   = string
                              options   = map(string)
                              read_only = bool
                              secret_ref = list(object(
                                {
                                  name      = string
                                  namespace = string
                                }
                              ))
                            }
                          ))
                          flocker = list(object(
                            {
                              dataset_name = string
                              dataset_uuid = string
                            }
                          ))
                          gce_persistent_disk = list(object(
                            {
                              fs_type   = string
                              partition = number
                              pd_name   = string
                              read_only = bool
                            }
                          ))
                          git_repo = list(object(
                            {
                              directory  = string
                              repository = string
                              revision   = string
                            }
                          ))
                          glusterfs = list(object(
                            {
                              endpoints_name = string
                              path           = string
                              read_only      = bool
                            }
                          ))
                          host_path = list(object(
                            {
                              path = string
                              type = string
                            }
                          ))
                          iscsi = list(object(
                            {
                              fs_type         = string
                              iqn             = string
                              iscsi_interface = string
                              lun             = number
                              read_only       = bool
                              target_portal   = string
                            }
                          ))
                          local = list(object(
                            {
                              path = string
                            }
                          ))
                          name = string
                          nfs = list(object(
                            {
                              path      = string
                              read_only = bool
                              server    = string
                            }
                          ))
                          persistent_volume_claim = list(object(
                            {
                              claim_name = string
                              read_only  = bool
                            }
                          ))
                          photon_persistent_disk = list(object(
                            {
                              fs_type = string
                              pd_id   = string
                            }
                          ))
                          projected = list(object(
                            {
                              default_mode = string
                              sources = list(object(
                                {
                                  config_map = list(object(
                                    {
                                      items = list(object(
                                        {
                                          key  = string
                                          mode = string
                                          path = string
                                        }
                                      ))
                                      name     = string
                                      optional = bool
                                    }
                                  ))
                                  downward_api = list(object(
                                    {
                                      items = list(object(
                                        {
                                          field_ref = list(object(
                                            {
                                              api_version = string
                                              field_path  = string
                                            }
                                          ))
                                          mode = string
                                          path = string
                                          resource_field_ref = list(object(
                                            {
                                              container_name = string
                                              divisor        = string
                                              resource       = string
                                            }
                                          ))
                                        }
                                      ))
                                    }
                                  ))
                                  secret = list(object(
                                    {
                                      items = list(object(
                                        {
                                          key  = string
                                          mode = string
                                          path = string
                                        }
                                      ))
                                      name     = string
                                      optional = bool
                                    }
                                  ))
                                  service_account_token = list(object(
                                    {
                                      audience           = string
                                      expiration_seconds = number
                                      path               = string
                                    }
                                  ))
                                }
                              ))
                            }
                          ))
                          quobyte = list(object(
                            {
                              group     = string
                              read_only = bool
                              registry  = string
                              user      = string
                              volume    = string
                            }
                          ))
                          rbd = list(object(
                            {
                              ceph_monitors = set(string)
                              fs_type       = string
                              keyring       = string
                              rados_user    = string
                              rbd_image     = string
                              rbd_pool      = string
                              read_only     = bool
                              secret_ref = list(object(
                                {
                                  name      = string
                                  namespace = string
                                }
                              ))
                            }
                          ))
                          secret = list(object(
                            {
                              default_mode = string
                              items = list(object(
                                {
                                  key  = string
                                  mode = string
                                  path = string
                                }
                              ))
                              optional    = bool
                              secret_name = string
                            }
                          ))
                          vsphere_volume = list(object(
                            {
                              fs_type     = string
                              volume_path = string
                            }
                          ))
                        }
                      ))
                    }
                  ))
                }
              ))
              ttl_seconds_after_finished = string
            }
          ))
        }
      ))
      schedule                      = string
      starting_deadline_seconds     = number
      successful_jobs_history_limit = number
      suspend                       = bool
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "kubernetes_cron_job" "this" {

  dynamic "metadata" {
    for_each = var.metadata
    content {
      annotations   = metadata.value["annotations"]
      generate_name = metadata.value["generate_name"]
      labels        = metadata.value["labels"]
      name          = metadata.value["name"]
      namespace     = metadata.value["namespace"]
    }
  }

  dynamic "spec" {
    for_each = var.spec
    content {
      concurrency_policy            = spec.value["concurrency_policy"]
      failed_jobs_history_limit     = spec.value["failed_jobs_history_limit"]
      schedule                      = spec.value["schedule"]
      starting_deadline_seconds     = spec.value["starting_deadline_seconds"]
      successful_jobs_history_limit = spec.value["successful_jobs_history_limit"]
      suspend                       = spec.value["suspend"]

      dynamic "job_template" {
        for_each = spec.value.job_template
        content {

          dynamic "metadata" {
            for_each = job_template.value.metadata
            content {
              annotations   = metadata.value["annotations"]
              generate_name = metadata.value["generate_name"]
              labels        = metadata.value["labels"]
              name          = metadata.value["name"]
            }
          }

          dynamic "spec" {
            for_each = job_template.value.spec
            content {
              active_deadline_seconds    = spec.value["active_deadline_seconds"]
              backoff_limit              = spec.value["backoff_limit"]
              completions                = spec.value["completions"]
              manual_selector            = spec.value["manual_selector"]
              parallelism                = spec.value["parallelism"]
              ttl_seconds_after_finished = spec.value["ttl_seconds_after_finished"]

              dynamic "selector" {
                for_each = spec.value.selector
                content {
                  match_labels = selector.value["match_labels"]

                  dynamic "match_expressions" {
                    for_each = selector.value.match_expressions
                    content {
                      key      = match_expressions.value["key"]
                      operator = match_expressions.value["operator"]
                      values   = match_expressions.value["values"]
                    }
                  }

                }
              }

              dynamic "template" {
                for_each = spec.value.template
                content {

                  dynamic "metadata" {
                    for_each = template.value.metadata
                    content {
                      annotations   = metadata.value["annotations"]
                      generate_name = metadata.value["generate_name"]
                      labels        = metadata.value["labels"]
                      name          = metadata.value["name"]
                    }
                  }

                  dynamic "spec" {
                    for_each = template.value.spec
                    content {
                      active_deadline_seconds          = spec.value["active_deadline_seconds"]
                      automount_service_account_token  = spec.value["automount_service_account_token"]
                      dns_policy                       = spec.value["dns_policy"]
                      enable_service_links             = spec.value["enable_service_links"]
                      host_ipc                         = spec.value["host_ipc"]
                      host_network                     = spec.value["host_network"]
                      host_pid                         = spec.value["host_pid"]
                      hostname                         = spec.value["hostname"]
                      node_name                        = spec.value["node_name"]
                      node_selector                    = spec.value["node_selector"]
                      priority_class_name              = spec.value["priority_class_name"]
                      restart_policy                   = spec.value["restart_policy"]
                      service_account_name             = spec.value["service_account_name"]
                      share_process_namespace          = spec.value["share_process_namespace"]
                      subdomain                        = spec.value["subdomain"]
                      termination_grace_period_seconds = spec.value["termination_grace_period_seconds"]

                      dynamic "affinity" {
                        for_each = spec.value.affinity
                        content {

                          dynamic "node_affinity" {
                            for_each = affinity.value.node_affinity
                            content {

                              dynamic "preferred_during_scheduling_ignored_during_execution" {
                                for_each = node_affinity.value.preferred_during_scheduling_ignored_during_execution
                                content {
                                  weight = preferred_during_scheduling_ignored_during_execution.value["weight"]

                                  dynamic "preference" {
                                    for_each = preferred_during_scheduling_ignored_during_execution.value.preference
                                    content {

                                      dynamic "match_expressions" {
                                        for_each = preference.value.match_expressions
                                        content {
                                          key      = match_expressions.value["key"]
                                          operator = match_expressions.value["operator"]
                                          values   = match_expressions.value["values"]
                                        }
                                      }

                                    }
                                  }

                                }
                              }

                              dynamic "required_during_scheduling_ignored_during_execution" {
                                for_each = node_affinity.value.required_during_scheduling_ignored_during_execution
                                content {

                                  dynamic "node_selector_term" {
                                    for_each = required_during_scheduling_ignored_during_execution.value.node_selector_term
                                    content {

                                      dynamic "match_expressions" {
                                        for_each = node_selector_term.value.match_expressions
                                        content {
                                          key      = match_expressions.value["key"]
                                          operator = match_expressions.value["operator"]
                                          values   = match_expressions.value["values"]
                                        }
                                      }

                                    }
                                  }

                                }
                              }

                            }
                          }

                          dynamic "pod_affinity" {
                            for_each = affinity.value.pod_affinity
                            content {

                              dynamic "preferred_during_scheduling_ignored_during_execution" {
                                for_each = pod_affinity.value.preferred_during_scheduling_ignored_during_execution
                                content {
                                  weight = preferred_during_scheduling_ignored_during_execution.value["weight"]

                                  dynamic "pod_affinity_term" {
                                    for_each = preferred_during_scheduling_ignored_during_execution.value.pod_affinity_term
                                    content {
                                      namespaces   = pod_affinity_term.value["namespaces"]
                                      topology_key = pod_affinity_term.value["topology_key"]

                                      dynamic "label_selector" {
                                        for_each = pod_affinity_term.value.label_selector
                                        content {
                                          match_labels = label_selector.value["match_labels"]

                                          dynamic "match_expressions" {
                                            for_each = label_selector.value.match_expressions
                                            content {
                                              key      = match_expressions.value["key"]
                                              operator = match_expressions.value["operator"]
                                              values   = match_expressions.value["values"]
                                            }
                                          }

                                        }
                                      }

                                    }
                                  }

                                }
                              }

                              dynamic "required_during_scheduling_ignored_during_execution" {
                                for_each = pod_affinity.value.required_during_scheduling_ignored_during_execution
                                content {
                                  namespaces   = required_during_scheduling_ignored_during_execution.value["namespaces"]
                                  topology_key = required_during_scheduling_ignored_during_execution.value["topology_key"]

                                  dynamic "label_selector" {
                                    for_each = required_during_scheduling_ignored_during_execution.value.label_selector
                                    content {
                                      match_labels = label_selector.value["match_labels"]

                                      dynamic "match_expressions" {
                                        for_each = label_selector.value.match_expressions
                                        content {
                                          key      = match_expressions.value["key"]
                                          operator = match_expressions.value["operator"]
                                          values   = match_expressions.value["values"]
                                        }
                                      }

                                    }
                                  }

                                }
                              }

                            }
                          }

                          dynamic "pod_anti_affinity" {
                            for_each = affinity.value.pod_anti_affinity
                            content {

                              dynamic "preferred_during_scheduling_ignored_during_execution" {
                                for_each = pod_anti_affinity.value.preferred_during_scheduling_ignored_during_execution
                                content {
                                  weight = preferred_during_scheduling_ignored_during_execution.value["weight"]

                                  dynamic "pod_affinity_term" {
                                    for_each = preferred_during_scheduling_ignored_during_execution.value.pod_affinity_term
                                    content {
                                      namespaces   = pod_affinity_term.value["namespaces"]
                                      topology_key = pod_affinity_term.value["topology_key"]

                                      dynamic "label_selector" {
                                        for_each = pod_affinity_term.value.label_selector
                                        content {
                                          match_labels = label_selector.value["match_labels"]

                                          dynamic "match_expressions" {
                                            for_each = label_selector.value.match_expressions
                                            content {
                                              key      = match_expressions.value["key"]
                                              operator = match_expressions.value["operator"]
                                              values   = match_expressions.value["values"]
                                            }
                                          }

                                        }
                                      }

                                    }
                                  }

                                }
                              }

                              dynamic "required_during_scheduling_ignored_during_execution" {
                                for_each = pod_anti_affinity.value.required_during_scheduling_ignored_during_execution
                                content {
                                  namespaces   = required_during_scheduling_ignored_during_execution.value["namespaces"]
                                  topology_key = required_during_scheduling_ignored_during_execution.value["topology_key"]

                                  dynamic "label_selector" {
                                    for_each = required_during_scheduling_ignored_during_execution.value.label_selector
                                    content {
                                      match_labels = label_selector.value["match_labels"]

                                      dynamic "match_expressions" {
                                        for_each = label_selector.value.match_expressions
                                        content {
                                          key      = match_expressions.value["key"]
                                          operator = match_expressions.value["operator"]
                                          values   = match_expressions.value["values"]
                                        }
                                      }

                                    }
                                  }

                                }
                              }

                            }
                          }

                        }
                      }

                      dynamic "container" {
                        for_each = spec.value.container
                        content {
                          args                       = container.value["args"]
                          command                    = container.value["command"]
                          image                      = container.value["image"]
                          image_pull_policy          = container.value["image_pull_policy"]
                          name                       = container.value["name"]
                          stdin                      = container.value["stdin"]
                          stdin_once                 = container.value["stdin_once"]
                          termination_message_path   = container.value["termination_message_path"]
                          termination_message_policy = container.value["termination_message_policy"]
                          tty                        = container.value["tty"]
                          working_dir                = container.value["working_dir"]

                          dynamic "env" {
                            for_each = container.value.env
                            content {
                              name  = env.value["name"]
                              value = env.value["value"]

                              dynamic "value_from" {
                                for_each = env.value.value_from
                                content {

                                  dynamic "config_map_key_ref" {
                                    for_each = value_from.value.config_map_key_ref
                                    content {
                                      key      = config_map_key_ref.value["key"]
                                      name     = config_map_key_ref.value["name"]
                                      optional = config_map_key_ref.value["optional"]
                                    }
                                  }

                                  dynamic "field_ref" {
                                    for_each = value_from.value.field_ref
                                    content {
                                      api_version = field_ref.value["api_version"]
                                      field_path  = field_ref.value["field_path"]
                                    }
                                  }

                                  dynamic "resource_field_ref" {
                                    for_each = value_from.value.resource_field_ref
                                    content {
                                      container_name = resource_field_ref.value["container_name"]
                                      divisor        = resource_field_ref.value["divisor"]
                                      resource       = resource_field_ref.value["resource"]
                                    }
                                  }

                                  dynamic "secret_key_ref" {
                                    for_each = value_from.value.secret_key_ref
                                    content {
                                      key      = secret_key_ref.value["key"]
                                      name     = secret_key_ref.value["name"]
                                      optional = secret_key_ref.value["optional"]
                                    }
                                  }

                                }
                              }

                            }
                          }

                          dynamic "env_from" {
                            for_each = container.value.env_from
                            content {
                              prefix = env_from.value["prefix"]

                              dynamic "config_map_ref" {
                                for_each = env_from.value.config_map_ref
                                content {
                                  name     = config_map_ref.value["name"]
                                  optional = config_map_ref.value["optional"]
                                }
                              }

                              dynamic "secret_ref" {
                                for_each = env_from.value.secret_ref
                                content {
                                  name     = secret_ref.value["name"]
                                  optional = secret_ref.value["optional"]
                                }
                              }

                            }
                          }

                          dynamic "lifecycle" {
                            for_each = container.value.lifecycle
                            content {

                              dynamic "post_start" {
                                for_each = lifecycle.value.post_start
                                content {

                                  dynamic "exec" {
                                    for_each = post_start.value.exec
                                    content {
                                      command = exec.value["command"]
                                    }
                                  }

                                  dynamic "http_get" {
                                    for_each = post_start.value.http_get
                                    content {
                                      host   = http_get.value["host"]
                                      path   = http_get.value["path"]
                                      port   = http_get.value["port"]
                                      scheme = http_get.value["scheme"]

                                      dynamic "http_header" {
                                        for_each = http_get.value.http_header
                                        content {
                                          name  = http_header.value["name"]
                                          value = http_header.value["value"]
                                        }
                                      }

                                    }
                                  }

                                  dynamic "tcp_socket" {
                                    for_each = post_start.value.tcp_socket
                                    content {
                                      port = tcp_socket.value["port"]
                                    }
                                  }

                                }
                              }

                              dynamic "pre_stop" {
                                for_each = lifecycle.value.pre_stop
                                content {

                                  dynamic "exec" {
                                    for_each = pre_stop.value.exec
                                    content {
                                      command = exec.value["command"]
                                    }
                                  }

                                  dynamic "http_get" {
                                    for_each = pre_stop.value.http_get
                                    content {
                                      host   = http_get.value["host"]
                                      path   = http_get.value["path"]
                                      port   = http_get.value["port"]
                                      scheme = http_get.value["scheme"]

                                      dynamic "http_header" {
                                        for_each = http_get.value.http_header
                                        content {
                                          name  = http_header.value["name"]
                                          value = http_header.value["value"]
                                        }
                                      }

                                    }
                                  }

                                  dynamic "tcp_socket" {
                                    for_each = pre_stop.value.tcp_socket
                                    content {
                                      port = tcp_socket.value["port"]
                                    }
                                  }

                                }
                              }

                            }
                          }

                          dynamic "liveness_probe" {
                            for_each = container.value.liveness_probe
                            content {
                              failure_threshold     = liveness_probe.value["failure_threshold"]
                              initial_delay_seconds = liveness_probe.value["initial_delay_seconds"]
                              period_seconds        = liveness_probe.value["period_seconds"]
                              success_threshold     = liveness_probe.value["success_threshold"]
                              timeout_seconds       = liveness_probe.value["timeout_seconds"]

                              dynamic "exec" {
                                for_each = liveness_probe.value.exec
                                content {
                                  command = exec.value["command"]
                                }
                              }

                              dynamic "http_get" {
                                for_each = liveness_probe.value.http_get
                                content {
                                  host   = http_get.value["host"]
                                  path   = http_get.value["path"]
                                  port   = http_get.value["port"]
                                  scheme = http_get.value["scheme"]

                                  dynamic "http_header" {
                                    for_each = http_get.value.http_header
                                    content {
                                      name  = http_header.value["name"]
                                      value = http_header.value["value"]
                                    }
                                  }

                                }
                              }

                              dynamic "tcp_socket" {
                                for_each = liveness_probe.value.tcp_socket
                                content {
                                  port = tcp_socket.value["port"]
                                }
                              }

                            }
                          }

                          dynamic "port" {
                            for_each = container.value.port
                            content {
                              container_port = port.value["container_port"]
                              host_ip        = port.value["host_ip"]
                              host_port      = port.value["host_port"]
                              name           = port.value["name"]
                              protocol       = port.value["protocol"]
                            }
                          }

                          dynamic "readiness_probe" {
                            for_each = container.value.readiness_probe
                            content {
                              failure_threshold     = readiness_probe.value["failure_threshold"]
                              initial_delay_seconds = readiness_probe.value["initial_delay_seconds"]
                              period_seconds        = readiness_probe.value["period_seconds"]
                              success_threshold     = readiness_probe.value["success_threshold"]
                              timeout_seconds       = readiness_probe.value["timeout_seconds"]

                              dynamic "exec" {
                                for_each = readiness_probe.value.exec
                                content {
                                  command = exec.value["command"]
                                }
                              }

                              dynamic "http_get" {
                                for_each = readiness_probe.value.http_get
                                content {
                                  host   = http_get.value["host"]
                                  path   = http_get.value["path"]
                                  port   = http_get.value["port"]
                                  scheme = http_get.value["scheme"]

                                  dynamic "http_header" {
                                    for_each = http_get.value.http_header
                                    content {
                                      name  = http_header.value["name"]
                                      value = http_header.value["value"]
                                    }
                                  }

                                }
                              }

                              dynamic "tcp_socket" {
                                for_each = readiness_probe.value.tcp_socket
                                content {
                                  port = tcp_socket.value["port"]
                                }
                              }

                            }
                          }

                          dynamic "resources" {
                            for_each = container.value.resources
                            content {
                              limits   = resources.value["limits"]
                              requests = resources.value["requests"]
                            }
                          }

                          dynamic "security_context" {
                            for_each = container.value.security_context
                            content {
                              allow_privilege_escalation = security_context.value["allow_privilege_escalation"]
                              privileged                 = security_context.value["privileged"]
                              read_only_root_filesystem  = security_context.value["read_only_root_filesystem"]
                              run_as_group               = security_context.value["run_as_group"]
                              run_as_non_root            = security_context.value["run_as_non_root"]
                              run_as_user                = security_context.value["run_as_user"]

                              dynamic "capabilities" {
                                for_each = security_context.value.capabilities
                                content {
                                  add  = capabilities.value["add"]
                                  drop = capabilities.value["drop"]
                                }
                              }

                              dynamic "se_linux_options" {
                                for_each = security_context.value.se_linux_options
                                content {
                                  level = se_linux_options.value["level"]
                                  role  = se_linux_options.value["role"]
                                  type  = se_linux_options.value["type"]
                                  user  = se_linux_options.value["user"]
                                }
                              }

                            }
                          }

                          dynamic "startup_probe" {
                            for_each = container.value.startup_probe
                            content {
                              failure_threshold     = startup_probe.value["failure_threshold"]
                              initial_delay_seconds = startup_probe.value["initial_delay_seconds"]
                              period_seconds        = startup_probe.value["period_seconds"]
                              success_threshold     = startup_probe.value["success_threshold"]
                              timeout_seconds       = startup_probe.value["timeout_seconds"]

                              dynamic "exec" {
                                for_each = startup_probe.value.exec
                                content {
                                  command = exec.value["command"]
                                }
                              }

                              dynamic "http_get" {
                                for_each = startup_probe.value.http_get
                                content {
                                  host   = http_get.value["host"]
                                  path   = http_get.value["path"]
                                  port   = http_get.value["port"]
                                  scheme = http_get.value["scheme"]

                                  dynamic "http_header" {
                                    for_each = http_get.value.http_header
                                    content {
                                      name  = http_header.value["name"]
                                      value = http_header.value["value"]
                                    }
                                  }

                                }
                              }

                              dynamic "tcp_socket" {
                                for_each = startup_probe.value.tcp_socket
                                content {
                                  port = tcp_socket.value["port"]
                                }
                              }

                            }
                          }

                          dynamic "volume_mount" {
                            for_each = container.value.volume_mount
                            content {
                              mount_path        = volume_mount.value["mount_path"]
                              mount_propagation = volume_mount.value["mount_propagation"]
                              name              = volume_mount.value["name"]
                              read_only         = volume_mount.value["read_only"]
                              sub_path          = volume_mount.value["sub_path"]
                            }
                          }

                        }
                      }

                      dynamic "dns_config" {
                        for_each = spec.value.dns_config
                        content {
                          nameservers = dns_config.value["nameservers"]
                          searches    = dns_config.value["searches"]

                          dynamic "option" {
                            for_each = dns_config.value.option
                            content {
                              name  = option.value["name"]
                              value = option.value["value"]
                            }
                          }

                        }
                      }

                      dynamic "host_aliases" {
                        for_each = spec.value.host_aliases
                        content {
                          hostnames = host_aliases.value["hostnames"]
                          ip        = host_aliases.value["ip"]
                        }
                      }

                      dynamic "image_pull_secrets" {
                        for_each = spec.value.image_pull_secrets
                        content {
                          name = image_pull_secrets.value["name"]
                        }
                      }

                      dynamic "init_container" {
                        for_each = spec.value.init_container
                        content {
                          args                       = init_container.value["args"]
                          command                    = init_container.value["command"]
                          image                      = init_container.value["image"]
                          image_pull_policy          = init_container.value["image_pull_policy"]
                          name                       = init_container.value["name"]
                          stdin                      = init_container.value["stdin"]
                          stdin_once                 = init_container.value["stdin_once"]
                          termination_message_path   = init_container.value["termination_message_path"]
                          termination_message_policy = init_container.value["termination_message_policy"]
                          tty                        = init_container.value["tty"]
                          working_dir                = init_container.value["working_dir"]

                          dynamic "env" {
                            for_each = init_container.value.env
                            content {
                              name  = env.value["name"]
                              value = env.value["value"]

                              dynamic "value_from" {
                                for_each = env.value.value_from
                                content {

                                  dynamic "config_map_key_ref" {
                                    for_each = value_from.value.config_map_key_ref
                                    content {
                                      key      = config_map_key_ref.value["key"]
                                      name     = config_map_key_ref.value["name"]
                                      optional = config_map_key_ref.value["optional"]
                                    }
                                  }

                                  dynamic "field_ref" {
                                    for_each = value_from.value.field_ref
                                    content {
                                      api_version = field_ref.value["api_version"]
                                      field_path  = field_ref.value["field_path"]
                                    }
                                  }

                                  dynamic "resource_field_ref" {
                                    for_each = value_from.value.resource_field_ref
                                    content {
                                      container_name = resource_field_ref.value["container_name"]
                                      divisor        = resource_field_ref.value["divisor"]
                                      resource       = resource_field_ref.value["resource"]
                                    }
                                  }

                                  dynamic "secret_key_ref" {
                                    for_each = value_from.value.secret_key_ref
                                    content {
                                      key      = secret_key_ref.value["key"]
                                      name     = secret_key_ref.value["name"]
                                      optional = secret_key_ref.value["optional"]
                                    }
                                  }

                                }
                              }

                            }
                          }

                          dynamic "env_from" {
                            for_each = init_container.value.env_from
                            content {
                              prefix = env_from.value["prefix"]

                              dynamic "config_map_ref" {
                                for_each = env_from.value.config_map_ref
                                content {
                                  name     = config_map_ref.value["name"]
                                  optional = config_map_ref.value["optional"]
                                }
                              }

                              dynamic "secret_ref" {
                                for_each = env_from.value.secret_ref
                                content {
                                  name     = secret_ref.value["name"]
                                  optional = secret_ref.value["optional"]
                                }
                              }

                            }
                          }

                          dynamic "lifecycle" {
                            for_each = init_container.value.lifecycle
                            content {

                              dynamic "post_start" {
                                for_each = lifecycle.value.post_start
                                content {

                                  dynamic "exec" {
                                    for_each = post_start.value.exec
                                    content {
                                      command = exec.value["command"]
                                    }
                                  }

                                  dynamic "http_get" {
                                    for_each = post_start.value.http_get
                                    content {
                                      host   = http_get.value["host"]
                                      path   = http_get.value["path"]
                                      port   = http_get.value["port"]
                                      scheme = http_get.value["scheme"]

                                      dynamic "http_header" {
                                        for_each = http_get.value.http_header
                                        content {
                                          name  = http_header.value["name"]
                                          value = http_header.value["value"]
                                        }
                                      }

                                    }
                                  }

                                  dynamic "tcp_socket" {
                                    for_each = post_start.value.tcp_socket
                                    content {
                                      port = tcp_socket.value["port"]
                                    }
                                  }

                                }
                              }

                              dynamic "pre_stop" {
                                for_each = lifecycle.value.pre_stop
                                content {

                                  dynamic "exec" {
                                    for_each = pre_stop.value.exec
                                    content {
                                      command = exec.value["command"]
                                    }
                                  }

                                  dynamic "http_get" {
                                    for_each = pre_stop.value.http_get
                                    content {
                                      host   = http_get.value["host"]
                                      path   = http_get.value["path"]
                                      port   = http_get.value["port"]
                                      scheme = http_get.value["scheme"]

                                      dynamic "http_header" {
                                        for_each = http_get.value.http_header
                                        content {
                                          name  = http_header.value["name"]
                                          value = http_header.value["value"]
                                        }
                                      }

                                    }
                                  }

                                  dynamic "tcp_socket" {
                                    for_each = pre_stop.value.tcp_socket
                                    content {
                                      port = tcp_socket.value["port"]
                                    }
                                  }

                                }
                              }

                            }
                          }

                          dynamic "liveness_probe" {
                            for_each = init_container.value.liveness_probe
                            content {
                              failure_threshold     = liveness_probe.value["failure_threshold"]
                              initial_delay_seconds = liveness_probe.value["initial_delay_seconds"]
                              period_seconds        = liveness_probe.value["period_seconds"]
                              success_threshold     = liveness_probe.value["success_threshold"]
                              timeout_seconds       = liveness_probe.value["timeout_seconds"]

                              dynamic "exec" {
                                for_each = liveness_probe.value.exec
                                content {
                                  command = exec.value["command"]
                                }
                              }

                              dynamic "http_get" {
                                for_each = liveness_probe.value.http_get
                                content {
                                  host   = http_get.value["host"]
                                  path   = http_get.value["path"]
                                  port   = http_get.value["port"]
                                  scheme = http_get.value["scheme"]

                                  dynamic "http_header" {
                                    for_each = http_get.value.http_header
                                    content {
                                      name  = http_header.value["name"]
                                      value = http_header.value["value"]
                                    }
                                  }

                                }
                              }

                              dynamic "tcp_socket" {
                                for_each = liveness_probe.value.tcp_socket
                                content {
                                  port = tcp_socket.value["port"]
                                }
                              }

                            }
                          }

                          dynamic "port" {
                            for_each = init_container.value.port
                            content {
                              container_port = port.value["container_port"]
                              host_ip        = port.value["host_ip"]
                              host_port      = port.value["host_port"]
                              name           = port.value["name"]
                              protocol       = port.value["protocol"]
                            }
                          }

                          dynamic "readiness_probe" {
                            for_each = init_container.value.readiness_probe
                            content {
                              failure_threshold     = readiness_probe.value["failure_threshold"]
                              initial_delay_seconds = readiness_probe.value["initial_delay_seconds"]
                              period_seconds        = readiness_probe.value["period_seconds"]
                              success_threshold     = readiness_probe.value["success_threshold"]
                              timeout_seconds       = readiness_probe.value["timeout_seconds"]

                              dynamic "exec" {
                                for_each = readiness_probe.value.exec
                                content {
                                  command = exec.value["command"]
                                }
                              }

                              dynamic "http_get" {
                                for_each = readiness_probe.value.http_get
                                content {
                                  host   = http_get.value["host"]
                                  path   = http_get.value["path"]
                                  port   = http_get.value["port"]
                                  scheme = http_get.value["scheme"]

                                  dynamic "http_header" {
                                    for_each = http_get.value.http_header
                                    content {
                                      name  = http_header.value["name"]
                                      value = http_header.value["value"]
                                    }
                                  }

                                }
                              }

                              dynamic "tcp_socket" {
                                for_each = readiness_probe.value.tcp_socket
                                content {
                                  port = tcp_socket.value["port"]
                                }
                              }

                            }
                          }

                          dynamic "resources" {
                            for_each = init_container.value.resources
                            content {
                              limits   = resources.value["limits"]
                              requests = resources.value["requests"]
                            }
                          }

                          dynamic "security_context" {
                            for_each = init_container.value.security_context
                            content {
                              allow_privilege_escalation = security_context.value["allow_privilege_escalation"]
                              privileged                 = security_context.value["privileged"]
                              read_only_root_filesystem  = security_context.value["read_only_root_filesystem"]
                              run_as_group               = security_context.value["run_as_group"]
                              run_as_non_root            = security_context.value["run_as_non_root"]
                              run_as_user                = security_context.value["run_as_user"]

                              dynamic "capabilities" {
                                for_each = security_context.value.capabilities
                                content {
                                  add  = capabilities.value["add"]
                                  drop = capabilities.value["drop"]
                                }
                              }

                              dynamic "se_linux_options" {
                                for_each = security_context.value.se_linux_options
                                content {
                                  level = se_linux_options.value["level"]
                                  role  = se_linux_options.value["role"]
                                  type  = se_linux_options.value["type"]
                                  user  = se_linux_options.value["user"]
                                }
                              }

                            }
                          }

                          dynamic "startup_probe" {
                            for_each = init_container.value.startup_probe
                            content {
                              failure_threshold     = startup_probe.value["failure_threshold"]
                              initial_delay_seconds = startup_probe.value["initial_delay_seconds"]
                              period_seconds        = startup_probe.value["period_seconds"]
                              success_threshold     = startup_probe.value["success_threshold"]
                              timeout_seconds       = startup_probe.value["timeout_seconds"]

                              dynamic "exec" {
                                for_each = startup_probe.value.exec
                                content {
                                  command = exec.value["command"]
                                }
                              }

                              dynamic "http_get" {
                                for_each = startup_probe.value.http_get
                                content {
                                  host   = http_get.value["host"]
                                  path   = http_get.value["path"]
                                  port   = http_get.value["port"]
                                  scheme = http_get.value["scheme"]

                                  dynamic "http_header" {
                                    for_each = http_get.value.http_header
                                    content {
                                      name  = http_header.value["name"]
                                      value = http_header.value["value"]
                                    }
                                  }

                                }
                              }

                              dynamic "tcp_socket" {
                                for_each = startup_probe.value.tcp_socket
                                content {
                                  port = tcp_socket.value["port"]
                                }
                              }

                            }
                          }

                          dynamic "volume_mount" {
                            for_each = init_container.value.volume_mount
                            content {
                              mount_path        = volume_mount.value["mount_path"]
                              mount_propagation = volume_mount.value["mount_propagation"]
                              name              = volume_mount.value["name"]
                              read_only         = volume_mount.value["read_only"]
                              sub_path          = volume_mount.value["sub_path"]
                            }
                          }

                        }
                      }

                      dynamic "readiness_gate" {
                        for_each = spec.value.readiness_gate
                        content {
                          condition_type = readiness_gate.value["condition_type"]
                        }
                      }

                      dynamic "security_context" {
                        for_each = spec.value.security_context
                        content {
                          fs_group            = security_context.value["fs_group"]
                          run_as_group        = security_context.value["run_as_group"]
                          run_as_non_root     = security_context.value["run_as_non_root"]
                          run_as_user         = security_context.value["run_as_user"]
                          supplemental_groups = security_context.value["supplemental_groups"]

                          dynamic "se_linux_options" {
                            for_each = security_context.value.se_linux_options
                            content {
                              level = se_linux_options.value["level"]
                              role  = se_linux_options.value["role"]
                              type  = se_linux_options.value["type"]
                              user  = se_linux_options.value["user"]
                            }
                          }

                          dynamic "sysctl" {
                            for_each = security_context.value.sysctl
                            content {
                              name  = sysctl.value["name"]
                              value = sysctl.value["value"]
                            }
                          }

                        }
                      }

                      dynamic "toleration" {
                        for_each = spec.value.toleration
                        content {
                          effect             = toleration.value["effect"]
                          key                = toleration.value["key"]
                          operator           = toleration.value["operator"]
                          toleration_seconds = toleration.value["toleration_seconds"]
                          value              = toleration.value["value"]
                        }
                      }

                      dynamic "topology_spread_constraint" {
                        for_each = spec.value.topology_spread_constraint
                        content {
                          max_skew           = topology_spread_constraint.value["max_skew"]
                          topology_key       = topology_spread_constraint.value["topology_key"]
                          when_unsatisfiable = topology_spread_constraint.value["when_unsatisfiable"]

                          dynamic "label_selector" {
                            for_each = topology_spread_constraint.value.label_selector
                            content {
                              match_labels = label_selector.value["match_labels"]

                              dynamic "match_expressions" {
                                for_each = label_selector.value.match_expressions
                                content {
                                  key      = match_expressions.value["key"]
                                  operator = match_expressions.value["operator"]
                                  values   = match_expressions.value["values"]
                                }
                              }

                            }
                          }

                        }
                      }

                      dynamic "volume" {
                        for_each = spec.value.volume
                        content {
                          name = volume.value["name"]

                          dynamic "aws_elastic_block_store" {
                            for_each = volume.value.aws_elastic_block_store
                            content {
                              fs_type   = aws_elastic_block_store.value["fs_type"]
                              partition = aws_elastic_block_store.value["partition"]
                              read_only = aws_elastic_block_store.value["read_only"]
                              volume_id = aws_elastic_block_store.value["volume_id"]
                            }
                          }

                          dynamic "azure_disk" {
                            for_each = volume.value.azure_disk
                            content {
                              caching_mode  = azure_disk.value["caching_mode"]
                              data_disk_uri = azure_disk.value["data_disk_uri"]
                              disk_name     = azure_disk.value["disk_name"]
                              fs_type       = azure_disk.value["fs_type"]
                              kind          = azure_disk.value["kind"]
                              read_only     = azure_disk.value["read_only"]
                            }
                          }

                          dynamic "azure_file" {
                            for_each = volume.value.azure_file
                            content {
                              read_only   = azure_file.value["read_only"]
                              secret_name = azure_file.value["secret_name"]
                              share_name  = azure_file.value["share_name"]
                            }
                          }

                          dynamic "ceph_fs" {
                            for_each = volume.value.ceph_fs
                            content {
                              monitors    = ceph_fs.value["monitors"]
                              path        = ceph_fs.value["path"]
                              read_only   = ceph_fs.value["read_only"]
                              secret_file = ceph_fs.value["secret_file"]
                              user        = ceph_fs.value["user"]

                              dynamic "secret_ref" {
                                for_each = ceph_fs.value.secret_ref
                                content {
                                  name      = secret_ref.value["name"]
                                  namespace = secret_ref.value["namespace"]
                                }
                              }

                            }
                          }

                          dynamic "cinder" {
                            for_each = volume.value.cinder
                            content {
                              fs_type   = cinder.value["fs_type"]
                              read_only = cinder.value["read_only"]
                              volume_id = cinder.value["volume_id"]
                            }
                          }

                          dynamic "config_map" {
                            for_each = volume.value.config_map
                            content {
                              default_mode = config_map.value["default_mode"]
                              name         = config_map.value["name"]
                              optional     = config_map.value["optional"]

                              dynamic "items" {
                                for_each = config_map.value.items
                                content {
                                  key  = items.value["key"]
                                  mode = items.value["mode"]
                                  path = items.value["path"]
                                }
                              }

                            }
                          }

                          dynamic "csi" {
                            for_each = volume.value.csi
                            content {
                              driver            = csi.value["driver"]
                              fs_type           = csi.value["fs_type"]
                              read_only         = csi.value["read_only"]
                              volume_attributes = csi.value["volume_attributes"]
                              volume_handle     = csi.value["volume_handle"]

                              dynamic "controller_expand_secret_ref" {
                                for_each = csi.value.controller_expand_secret_ref
                                content {
                                  name      = controller_expand_secret_ref.value["name"]
                                  namespace = controller_expand_secret_ref.value["namespace"]
                                }
                              }

                              dynamic "controller_publish_secret_ref" {
                                for_each = csi.value.controller_publish_secret_ref
                                content {
                                  name      = controller_publish_secret_ref.value["name"]
                                  namespace = controller_publish_secret_ref.value["namespace"]
                                }
                              }

                              dynamic "node_publish_secret_ref" {
                                for_each = csi.value.node_publish_secret_ref
                                content {
                                  name      = node_publish_secret_ref.value["name"]
                                  namespace = node_publish_secret_ref.value["namespace"]
                                }
                              }

                              dynamic "node_stage_secret_ref" {
                                for_each = csi.value.node_stage_secret_ref
                                content {
                                  name      = node_stage_secret_ref.value["name"]
                                  namespace = node_stage_secret_ref.value["namespace"]
                                }
                              }

                            }
                          }

                          dynamic "downward_api" {
                            for_each = volume.value.downward_api
                            content {
                              default_mode = downward_api.value["default_mode"]

                              dynamic "items" {
                                for_each = downward_api.value.items
                                content {
                                  mode = items.value["mode"]
                                  path = items.value["path"]

                                  dynamic "field_ref" {
                                    for_each = items.value.field_ref
                                    content {
                                      api_version = field_ref.value["api_version"]
                                      field_path  = field_ref.value["field_path"]
                                    }
                                  }

                                  dynamic "resource_field_ref" {
                                    for_each = items.value.resource_field_ref
                                    content {
                                      container_name = resource_field_ref.value["container_name"]
                                      divisor        = resource_field_ref.value["divisor"]
                                      resource       = resource_field_ref.value["resource"]
                                    }
                                  }

                                }
                              }

                            }
                          }

                          dynamic "empty_dir" {
                            for_each = volume.value.empty_dir
                            content {
                              medium     = empty_dir.value["medium"]
                              size_limit = empty_dir.value["size_limit"]
                            }
                          }

                          dynamic "fc" {
                            for_each = volume.value.fc
                            content {
                              fs_type      = fc.value["fs_type"]
                              lun          = fc.value["lun"]
                              read_only    = fc.value["read_only"]
                              target_ww_ns = fc.value["target_ww_ns"]
                            }
                          }

                          dynamic "flex_volume" {
                            for_each = volume.value.flex_volume
                            content {
                              driver    = flex_volume.value["driver"]
                              fs_type   = flex_volume.value["fs_type"]
                              options   = flex_volume.value["options"]
                              read_only = flex_volume.value["read_only"]

                              dynamic "secret_ref" {
                                for_each = flex_volume.value.secret_ref
                                content {
                                  name      = secret_ref.value["name"]
                                  namespace = secret_ref.value["namespace"]
                                }
                              }

                            }
                          }

                          dynamic "flocker" {
                            for_each = volume.value.flocker
                            content {
                              dataset_name = flocker.value["dataset_name"]
                              dataset_uuid = flocker.value["dataset_uuid"]
                            }
                          }

                          dynamic "gce_persistent_disk" {
                            for_each = volume.value.gce_persistent_disk
                            content {
                              fs_type   = gce_persistent_disk.value["fs_type"]
                              partition = gce_persistent_disk.value["partition"]
                              pd_name   = gce_persistent_disk.value["pd_name"]
                              read_only = gce_persistent_disk.value["read_only"]
                            }
                          }

                          dynamic "git_repo" {
                            for_each = volume.value.git_repo
                            content {
                              directory  = git_repo.value["directory"]
                              repository = git_repo.value["repository"]
                              revision   = git_repo.value["revision"]
                            }
                          }

                          dynamic "glusterfs" {
                            for_each = volume.value.glusterfs
                            content {
                              endpoints_name = glusterfs.value["endpoints_name"]
                              path           = glusterfs.value["path"]
                              read_only      = glusterfs.value["read_only"]
                            }
                          }

                          dynamic "host_path" {
                            for_each = volume.value.host_path
                            content {
                              path = host_path.value["path"]
                              type = host_path.value["type"]
                            }
                          }

                          dynamic "iscsi" {
                            for_each = volume.value.iscsi
                            content {
                              fs_type         = iscsi.value["fs_type"]
                              iqn             = iscsi.value["iqn"]
                              iscsi_interface = iscsi.value["iscsi_interface"]
                              lun             = iscsi.value["lun"]
                              read_only       = iscsi.value["read_only"]
                              target_portal   = iscsi.value["target_portal"]
                            }
                          }

                          dynamic "local" {
                            for_each = volume.value.local
                            content {
                              path = local.value["path"]
                            }
                          }

                          dynamic "nfs" {
                            for_each = volume.value.nfs
                            content {
                              path      = nfs.value["path"]
                              read_only = nfs.value["read_only"]
                              server    = nfs.value["server"]
                            }
                          }

                          dynamic "persistent_volume_claim" {
                            for_each = volume.value.persistent_volume_claim
                            content {
                              claim_name = persistent_volume_claim.value["claim_name"]
                              read_only  = persistent_volume_claim.value["read_only"]
                            }
                          }

                          dynamic "photon_persistent_disk" {
                            for_each = volume.value.photon_persistent_disk
                            content {
                              fs_type = photon_persistent_disk.value["fs_type"]
                              pd_id   = photon_persistent_disk.value["pd_id"]
                            }
                          }

                          dynamic "projected" {
                            for_each = volume.value.projected
                            content {
                              default_mode = projected.value["default_mode"]

                              dynamic "sources" {
                                for_each = projected.value.sources
                                content {

                                  dynamic "config_map" {
                                    for_each = sources.value.config_map
                                    content {
                                      name     = config_map.value["name"]
                                      optional = config_map.value["optional"]

                                      dynamic "items" {
                                        for_each = config_map.value.items
                                        content {
                                          key  = items.value["key"]
                                          mode = items.value["mode"]
                                          path = items.value["path"]
                                        }
                                      }

                                    }
                                  }

                                  dynamic "downward_api" {
                                    for_each = sources.value.downward_api
                                    content {

                                      dynamic "items" {
                                        for_each = downward_api.value.items
                                        content {
                                          mode = items.value["mode"]
                                          path = items.value["path"]

                                          dynamic "field_ref" {
                                            for_each = items.value.field_ref
                                            content {
                                              api_version = field_ref.value["api_version"]
                                              field_path  = field_ref.value["field_path"]
                                            }
                                          }

                                          dynamic "resource_field_ref" {
                                            for_each = items.value.resource_field_ref
                                            content {
                                              container_name = resource_field_ref.value["container_name"]
                                              divisor        = resource_field_ref.value["divisor"]
                                              resource       = resource_field_ref.value["resource"]
                                            }
                                          }

                                        }
                                      }

                                    }
                                  }

                                  dynamic "secret" {
                                    for_each = sources.value.secret
                                    content {
                                      name     = secret.value["name"]
                                      optional = secret.value["optional"]

                                      dynamic "items" {
                                        for_each = secret.value.items
                                        content {
                                          key  = items.value["key"]
                                          mode = items.value["mode"]
                                          path = items.value["path"]
                                        }
                                      }

                                    }
                                  }

                                  dynamic "service_account_token" {
                                    for_each = sources.value.service_account_token
                                    content {
                                      audience           = service_account_token.value["audience"]
                                      expiration_seconds = service_account_token.value["expiration_seconds"]
                                      path               = service_account_token.value["path"]
                                    }
                                  }

                                }
                              }

                            }
                          }

                          dynamic "quobyte" {
                            for_each = volume.value.quobyte
                            content {
                              group     = quobyte.value["group"]
                              read_only = quobyte.value["read_only"]
                              registry  = quobyte.value["registry"]
                              user      = quobyte.value["user"]
                              volume    = quobyte.value["volume"]
                            }
                          }

                          dynamic "rbd" {
                            for_each = volume.value.rbd
                            content {
                              ceph_monitors = rbd.value["ceph_monitors"]
                              fs_type       = rbd.value["fs_type"]
                              keyring       = rbd.value["keyring"]
                              rados_user    = rbd.value["rados_user"]
                              rbd_image     = rbd.value["rbd_image"]
                              rbd_pool      = rbd.value["rbd_pool"]
                              read_only     = rbd.value["read_only"]

                              dynamic "secret_ref" {
                                for_each = rbd.value.secret_ref
                                content {
                                  name      = secret_ref.value["name"]
                                  namespace = secret_ref.value["namespace"]
                                }
                              }

                            }
                          }

                          dynamic "secret" {
                            for_each = volume.value.secret
                            content {
                              default_mode = secret.value["default_mode"]
                              optional     = secret.value["optional"]
                              secret_name  = secret.value["secret_name"]

                              dynamic "items" {
                                for_each = secret.value.items
                                content {
                                  key  = items.value["key"]
                                  mode = items.value["mode"]
                                  path = items.value["path"]
                                }
                              }

                            }
                          }

                          dynamic "vsphere_volume" {
                            for_each = volume.value.vsphere_volume
                            content {
                              fs_type     = vsphere_volume.value["fs_type"]
                              volume_path = vsphere_volume.value["volume_path"]
                            }
                          }

                        }
                      }

                    }
                  }

                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = kubernetes_cron_job.this.id
}

output "this" {
  value = kubernetes_cron_job.this
}
```

[top](#index)