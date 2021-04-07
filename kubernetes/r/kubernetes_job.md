# kubernetes_job

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
module "kubernetes_job" {
  source = "./modules/kubernetes/r/kubernetes_job"

  # wait_for_completion - (optional) is a type of bool
  wait_for_completion = null

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

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "wait_for_completion" {
  description = "(optional)"
  type        = bool
  default     = null
}

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

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "kubernetes_job" "this" {
  # wait_for_completion - (optional) is a type of bool
  wait_for_completion = var.wait_for_completion

  dynamic "metadata" {
    for_each = var.metadata
    content {
      # annotations - (optional) is a type of map of string
      annotations = metadata.value["annotations"]
      # generate_name - (optional) is a type of string
      generate_name = metadata.value["generate_name"]
      # labels - (optional) is a type of map of string
      labels = metadata.value["labels"]
      # name - (optional) is a type of string
      name = metadata.value["name"]
      # namespace - (optional) is a type of string
      namespace = metadata.value["namespace"]
    }
  }

  dynamic "spec" {
    for_each = var.spec
    content {
      # active_deadline_seconds - (optional) is a type of number
      active_deadline_seconds = spec.value["active_deadline_seconds"]
      # backoff_limit - (optional) is a type of number
      backoff_limit = spec.value["backoff_limit"]
      # completions - (optional) is a type of number
      completions = spec.value["completions"]
      # manual_selector - (optional) is a type of bool
      manual_selector = spec.value["manual_selector"]
      # parallelism - (optional) is a type of number
      parallelism = spec.value["parallelism"]
      # ttl_seconds_after_finished - (optional) is a type of string
      ttl_seconds_after_finished = spec.value["ttl_seconds_after_finished"]

      dynamic "selector" {
        for_each = spec.value.selector
        content {
          # match_labels - (optional) is a type of map of string
          match_labels = selector.value["match_labels"]

          dynamic "match_expressions" {
            for_each = selector.value.match_expressions
            content {
              # key - (optional) is a type of string
              key = match_expressions.value["key"]
              # operator - (optional) is a type of string
              operator = match_expressions.value["operator"]
              # values - (optional) is a type of set of string
              values = match_expressions.value["values"]
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
              # annotations - (optional) is a type of map of string
              annotations = metadata.value["annotations"]
              # generate_name - (optional) is a type of string
              generate_name = metadata.value["generate_name"]
              # labels - (optional) is a type of map of string
              labels = metadata.value["labels"]
              # name - (optional) is a type of string
              name = metadata.value["name"]
            }
          }

          dynamic "spec" {
            for_each = template.value.spec
            content {
              # active_deadline_seconds - (optional) is a type of number
              active_deadline_seconds = spec.value["active_deadline_seconds"]
              # automount_service_account_token - (optional) is a type of bool
              automount_service_account_token = spec.value["automount_service_account_token"]
              # dns_policy - (optional) is a type of string
              dns_policy = spec.value["dns_policy"]
              # enable_service_links - (optional) is a type of bool
              enable_service_links = spec.value["enable_service_links"]
              # host_ipc - (optional) is a type of bool
              host_ipc = spec.value["host_ipc"]
              # host_network - (optional) is a type of bool
              host_network = spec.value["host_network"]
              # host_pid - (optional) is a type of bool
              host_pid = spec.value["host_pid"]
              # hostname - (optional) is a type of string
              hostname = spec.value["hostname"]
              # node_name - (optional) is a type of string
              node_name = spec.value["node_name"]
              # node_selector - (optional) is a type of map of string
              node_selector = spec.value["node_selector"]
              # priority_class_name - (optional) is a type of string
              priority_class_name = spec.value["priority_class_name"]
              # restart_policy - (optional) is a type of string
              restart_policy = spec.value["restart_policy"]
              # service_account_name - (optional) is a type of string
              service_account_name = spec.value["service_account_name"]
              # share_process_namespace - (optional) is a type of bool
              share_process_namespace = spec.value["share_process_namespace"]
              # subdomain - (optional) is a type of string
              subdomain = spec.value["subdomain"]
              # termination_grace_period_seconds - (optional) is a type of number
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
                          # weight - (required) is a type of number
                          weight = preferred_during_scheduling_ignored_during_execution.value["weight"]

                          dynamic "preference" {
                            for_each = preferred_during_scheduling_ignored_during_execution.value.preference
                            content {

                              dynamic "match_expressions" {
                                for_each = preference.value.match_expressions
                                content {
                                  # key - (optional) is a type of string
                                  key = match_expressions.value["key"]
                                  # operator - (optional) is a type of string
                                  operator = match_expressions.value["operator"]
                                  # values - (optional) is a type of set of string
                                  values = match_expressions.value["values"]
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
                                  # key - (optional) is a type of string
                                  key = match_expressions.value["key"]
                                  # operator - (optional) is a type of string
                                  operator = match_expressions.value["operator"]
                                  # values - (optional) is a type of set of string
                                  values = match_expressions.value["values"]
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
                          # weight - (required) is a type of number
                          weight = preferred_during_scheduling_ignored_during_execution.value["weight"]

                          dynamic "pod_affinity_term" {
                            for_each = preferred_during_scheduling_ignored_during_execution.value.pod_affinity_term
                            content {
                              # namespaces - (optional) is a type of set of string
                              namespaces = pod_affinity_term.value["namespaces"]
                              # topology_key - (optional) is a type of string
                              topology_key = pod_affinity_term.value["topology_key"]

                              dynamic "label_selector" {
                                for_each = pod_affinity_term.value.label_selector
                                content {
                                  # match_labels - (optional) is a type of map of string
                                  match_labels = label_selector.value["match_labels"]

                                  dynamic "match_expressions" {
                                    for_each = label_selector.value.match_expressions
                                    content {
                                      # key - (optional) is a type of string
                                      key = match_expressions.value["key"]
                                      # operator - (optional) is a type of string
                                      operator = match_expressions.value["operator"]
                                      # values - (optional) is a type of set of string
                                      values = match_expressions.value["values"]
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
                          # namespaces - (optional) is a type of set of string
                          namespaces = required_during_scheduling_ignored_during_execution.value["namespaces"]
                          # topology_key - (optional) is a type of string
                          topology_key = required_during_scheduling_ignored_during_execution.value["topology_key"]

                          dynamic "label_selector" {
                            for_each = required_during_scheduling_ignored_during_execution.value.label_selector
                            content {
                              # match_labels - (optional) is a type of map of string
                              match_labels = label_selector.value["match_labels"]

                              dynamic "match_expressions" {
                                for_each = label_selector.value.match_expressions
                                content {
                                  # key - (optional) is a type of string
                                  key = match_expressions.value["key"]
                                  # operator - (optional) is a type of string
                                  operator = match_expressions.value["operator"]
                                  # values - (optional) is a type of set of string
                                  values = match_expressions.value["values"]
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
                          # weight - (required) is a type of number
                          weight = preferred_during_scheduling_ignored_during_execution.value["weight"]

                          dynamic "pod_affinity_term" {
                            for_each = preferred_during_scheduling_ignored_during_execution.value.pod_affinity_term
                            content {
                              # namespaces - (optional) is a type of set of string
                              namespaces = pod_affinity_term.value["namespaces"]
                              # topology_key - (optional) is a type of string
                              topology_key = pod_affinity_term.value["topology_key"]

                              dynamic "label_selector" {
                                for_each = pod_affinity_term.value.label_selector
                                content {
                                  # match_labels - (optional) is a type of map of string
                                  match_labels = label_selector.value["match_labels"]

                                  dynamic "match_expressions" {
                                    for_each = label_selector.value.match_expressions
                                    content {
                                      # key - (optional) is a type of string
                                      key = match_expressions.value["key"]
                                      # operator - (optional) is a type of string
                                      operator = match_expressions.value["operator"]
                                      # values - (optional) is a type of set of string
                                      values = match_expressions.value["values"]
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
                          # namespaces - (optional) is a type of set of string
                          namespaces = required_during_scheduling_ignored_during_execution.value["namespaces"]
                          # topology_key - (optional) is a type of string
                          topology_key = required_during_scheduling_ignored_during_execution.value["topology_key"]

                          dynamic "label_selector" {
                            for_each = required_during_scheduling_ignored_during_execution.value.label_selector
                            content {
                              # match_labels - (optional) is a type of map of string
                              match_labels = label_selector.value["match_labels"]

                              dynamic "match_expressions" {
                                for_each = label_selector.value.match_expressions
                                content {
                                  # key - (optional) is a type of string
                                  key = match_expressions.value["key"]
                                  # operator - (optional) is a type of string
                                  operator = match_expressions.value["operator"]
                                  # values - (optional) is a type of set of string
                                  values = match_expressions.value["values"]
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
                  # args - (optional) is a type of list of string
                  args = container.value["args"]
                  # command - (optional) is a type of list of string
                  command = container.value["command"]
                  # image - (optional) is a type of string
                  image = container.value["image"]
                  # image_pull_policy - (optional) is a type of string
                  image_pull_policy = container.value["image_pull_policy"]
                  # name - (required) is a type of string
                  name = container.value["name"]
                  # stdin - (optional) is a type of bool
                  stdin = container.value["stdin"]
                  # stdin_once - (optional) is a type of bool
                  stdin_once = container.value["stdin_once"]
                  # termination_message_path - (optional) is a type of string
                  termination_message_path = container.value["termination_message_path"]
                  # termination_message_policy - (optional) is a type of string
                  termination_message_policy = container.value["termination_message_policy"]
                  # tty - (optional) is a type of bool
                  tty = container.value["tty"]
                  # working_dir - (optional) is a type of string
                  working_dir = container.value["working_dir"]

                  dynamic "env" {
                    for_each = container.value.env
                    content {
                      # name - (required) is a type of string
                      name = env.value["name"]
                      # value - (optional) is a type of string
                      value = env.value["value"]

                      dynamic "value_from" {
                        for_each = env.value.value_from
                        content {

                          dynamic "config_map_key_ref" {
                            for_each = value_from.value.config_map_key_ref
                            content {
                              # key - (optional) is a type of string
                              key = config_map_key_ref.value["key"]
                              # name - (optional) is a type of string
                              name = config_map_key_ref.value["name"]
                              # optional - (optional) is a type of bool
                              optional = config_map_key_ref.value["optional"]
                            }
                          }

                          dynamic "field_ref" {
                            for_each = value_from.value.field_ref
                            content {
                              # api_version - (optional) is a type of string
                              api_version = field_ref.value["api_version"]
                              # field_path - (optional) is a type of string
                              field_path = field_ref.value["field_path"]
                            }
                          }

                          dynamic "resource_field_ref" {
                            for_each = value_from.value.resource_field_ref
                            content {
                              # container_name - (optional) is a type of string
                              container_name = resource_field_ref.value["container_name"]
                              # divisor - (optional) is a type of string
                              divisor = resource_field_ref.value["divisor"]
                              # resource - (required) is a type of string
                              resource = resource_field_ref.value["resource"]
                            }
                          }

                          dynamic "secret_key_ref" {
                            for_each = value_from.value.secret_key_ref
                            content {
                              # key - (optional) is a type of string
                              key = secret_key_ref.value["key"]
                              # name - (optional) is a type of string
                              name = secret_key_ref.value["name"]
                              # optional - (optional) is a type of bool
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
                      # prefix - (optional) is a type of string
                      prefix = env_from.value["prefix"]

                      dynamic "config_map_ref" {
                        for_each = env_from.value.config_map_ref
                        content {
                          # name - (required) is a type of string
                          name = config_map_ref.value["name"]
                          # optional - (optional) is a type of bool
                          optional = config_map_ref.value["optional"]
                        }
                      }

                      dynamic "secret_ref" {
                        for_each = env_from.value.secret_ref
                        content {
                          # name - (required) is a type of string
                          name = secret_ref.value["name"]
                          # optional - (optional) is a type of bool
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
                              # command - (optional) is a type of list of string
                              command = exec.value["command"]
                            }
                          }

                          dynamic "http_get" {
                            for_each = post_start.value.http_get
                            content {
                              # host - (optional) is a type of string
                              host = http_get.value["host"]
                              # path - (optional) is a type of string
                              path = http_get.value["path"]
                              # port - (optional) is a type of string
                              port = http_get.value["port"]
                              # scheme - (optional) is a type of string
                              scheme = http_get.value["scheme"]

                              dynamic "http_header" {
                                for_each = http_get.value.http_header
                                content {
                                  # name - (optional) is a type of string
                                  name = http_header.value["name"]
                                  # value - (optional) is a type of string
                                  value = http_header.value["value"]
                                }
                              }

                            }
                          }

                          dynamic "tcp_socket" {
                            for_each = post_start.value.tcp_socket
                            content {
                              # port - (required) is a type of string
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
                              # command - (optional) is a type of list of string
                              command = exec.value["command"]
                            }
                          }

                          dynamic "http_get" {
                            for_each = pre_stop.value.http_get
                            content {
                              # host - (optional) is a type of string
                              host = http_get.value["host"]
                              # path - (optional) is a type of string
                              path = http_get.value["path"]
                              # port - (optional) is a type of string
                              port = http_get.value["port"]
                              # scheme - (optional) is a type of string
                              scheme = http_get.value["scheme"]

                              dynamic "http_header" {
                                for_each = http_get.value.http_header
                                content {
                                  # name - (optional) is a type of string
                                  name = http_header.value["name"]
                                  # value - (optional) is a type of string
                                  value = http_header.value["value"]
                                }
                              }

                            }
                          }

                          dynamic "tcp_socket" {
                            for_each = pre_stop.value.tcp_socket
                            content {
                              # port - (required) is a type of string
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
                      # failure_threshold - (optional) is a type of number
                      failure_threshold = liveness_probe.value["failure_threshold"]
                      # initial_delay_seconds - (optional) is a type of number
                      initial_delay_seconds = liveness_probe.value["initial_delay_seconds"]
                      # period_seconds - (optional) is a type of number
                      period_seconds = liveness_probe.value["period_seconds"]
                      # success_threshold - (optional) is a type of number
                      success_threshold = liveness_probe.value["success_threshold"]
                      # timeout_seconds - (optional) is a type of number
                      timeout_seconds = liveness_probe.value["timeout_seconds"]

                      dynamic "exec" {
                        for_each = liveness_probe.value.exec
                        content {
                          # command - (optional) is a type of list of string
                          command = exec.value["command"]
                        }
                      }

                      dynamic "http_get" {
                        for_each = liveness_probe.value.http_get
                        content {
                          # host - (optional) is a type of string
                          host = http_get.value["host"]
                          # path - (optional) is a type of string
                          path = http_get.value["path"]
                          # port - (optional) is a type of string
                          port = http_get.value["port"]
                          # scheme - (optional) is a type of string
                          scheme = http_get.value["scheme"]

                          dynamic "http_header" {
                            for_each = http_get.value.http_header
                            content {
                              # name - (optional) is a type of string
                              name = http_header.value["name"]
                              # value - (optional) is a type of string
                              value = http_header.value["value"]
                            }
                          }

                        }
                      }

                      dynamic "tcp_socket" {
                        for_each = liveness_probe.value.tcp_socket
                        content {
                          # port - (required) is a type of string
                          port = tcp_socket.value["port"]
                        }
                      }

                    }
                  }

                  dynamic "port" {
                    for_each = container.value.port
                    content {
                      # container_port - (required) is a type of number
                      container_port = port.value["container_port"]
                      # host_ip - (optional) is a type of string
                      host_ip = port.value["host_ip"]
                      # host_port - (optional) is a type of number
                      host_port = port.value["host_port"]
                      # name - (optional) is a type of string
                      name = port.value["name"]
                      # protocol - (optional) is a type of string
                      protocol = port.value["protocol"]
                    }
                  }

                  dynamic "readiness_probe" {
                    for_each = container.value.readiness_probe
                    content {
                      # failure_threshold - (optional) is a type of number
                      failure_threshold = readiness_probe.value["failure_threshold"]
                      # initial_delay_seconds - (optional) is a type of number
                      initial_delay_seconds = readiness_probe.value["initial_delay_seconds"]
                      # period_seconds - (optional) is a type of number
                      period_seconds = readiness_probe.value["period_seconds"]
                      # success_threshold - (optional) is a type of number
                      success_threshold = readiness_probe.value["success_threshold"]
                      # timeout_seconds - (optional) is a type of number
                      timeout_seconds = readiness_probe.value["timeout_seconds"]

                      dynamic "exec" {
                        for_each = readiness_probe.value.exec
                        content {
                          # command - (optional) is a type of list of string
                          command = exec.value["command"]
                        }
                      }

                      dynamic "http_get" {
                        for_each = readiness_probe.value.http_get
                        content {
                          # host - (optional) is a type of string
                          host = http_get.value["host"]
                          # path - (optional) is a type of string
                          path = http_get.value["path"]
                          # port - (optional) is a type of string
                          port = http_get.value["port"]
                          # scheme - (optional) is a type of string
                          scheme = http_get.value["scheme"]

                          dynamic "http_header" {
                            for_each = http_get.value.http_header
                            content {
                              # name - (optional) is a type of string
                              name = http_header.value["name"]
                              # value - (optional) is a type of string
                              value = http_header.value["value"]
                            }
                          }

                        }
                      }

                      dynamic "tcp_socket" {
                        for_each = readiness_probe.value.tcp_socket
                        content {
                          # port - (required) is a type of string
                          port = tcp_socket.value["port"]
                        }
                      }

                    }
                  }

                  dynamic "resources" {
                    for_each = container.value.resources
                    content {
                      # limits - (optional) is a type of map of string
                      limits = resources.value["limits"]
                      # requests - (optional) is a type of map of string
                      requests = resources.value["requests"]
                    }
                  }

                  dynamic "security_context" {
                    for_each = container.value.security_context
                    content {
                      # allow_privilege_escalation - (optional) is a type of bool
                      allow_privilege_escalation = security_context.value["allow_privilege_escalation"]
                      # privileged - (optional) is a type of bool
                      privileged = security_context.value["privileged"]
                      # read_only_root_filesystem - (optional) is a type of bool
                      read_only_root_filesystem = security_context.value["read_only_root_filesystem"]
                      # run_as_group - (optional) is a type of string
                      run_as_group = security_context.value["run_as_group"]
                      # run_as_non_root - (optional) is a type of bool
                      run_as_non_root = security_context.value["run_as_non_root"]
                      # run_as_user - (optional) is a type of string
                      run_as_user = security_context.value["run_as_user"]

                      dynamic "capabilities" {
                        for_each = security_context.value.capabilities
                        content {
                          # add - (optional) is a type of list of string
                          add = capabilities.value["add"]
                          # drop - (optional) is a type of list of string
                          drop = capabilities.value["drop"]
                        }
                      }

                      dynamic "se_linux_options" {
                        for_each = security_context.value.se_linux_options
                        content {
                          # level - (optional) is a type of string
                          level = se_linux_options.value["level"]
                          # role - (optional) is a type of string
                          role = se_linux_options.value["role"]
                          # type - (optional) is a type of string
                          type = se_linux_options.value["type"]
                          # user - (optional) is a type of string
                          user = se_linux_options.value["user"]
                        }
                      }

                    }
                  }

                  dynamic "startup_probe" {
                    for_each = container.value.startup_probe
                    content {
                      # failure_threshold - (optional) is a type of number
                      failure_threshold = startup_probe.value["failure_threshold"]
                      # initial_delay_seconds - (optional) is a type of number
                      initial_delay_seconds = startup_probe.value["initial_delay_seconds"]
                      # period_seconds - (optional) is a type of number
                      period_seconds = startup_probe.value["period_seconds"]
                      # success_threshold - (optional) is a type of number
                      success_threshold = startup_probe.value["success_threshold"]
                      # timeout_seconds - (optional) is a type of number
                      timeout_seconds = startup_probe.value["timeout_seconds"]

                      dynamic "exec" {
                        for_each = startup_probe.value.exec
                        content {
                          # command - (optional) is a type of list of string
                          command = exec.value["command"]
                        }
                      }

                      dynamic "http_get" {
                        for_each = startup_probe.value.http_get
                        content {
                          # host - (optional) is a type of string
                          host = http_get.value["host"]
                          # path - (optional) is a type of string
                          path = http_get.value["path"]
                          # port - (optional) is a type of string
                          port = http_get.value["port"]
                          # scheme - (optional) is a type of string
                          scheme = http_get.value["scheme"]

                          dynamic "http_header" {
                            for_each = http_get.value.http_header
                            content {
                              # name - (optional) is a type of string
                              name = http_header.value["name"]
                              # value - (optional) is a type of string
                              value = http_header.value["value"]
                            }
                          }

                        }
                      }

                      dynamic "tcp_socket" {
                        for_each = startup_probe.value.tcp_socket
                        content {
                          # port - (required) is a type of string
                          port = tcp_socket.value["port"]
                        }
                      }

                    }
                  }

                  dynamic "volume_mount" {
                    for_each = container.value.volume_mount
                    content {
                      # mount_path - (required) is a type of string
                      mount_path = volume_mount.value["mount_path"]
                      # mount_propagation - (optional) is a type of string
                      mount_propagation = volume_mount.value["mount_propagation"]
                      # name - (required) is a type of string
                      name = volume_mount.value["name"]
                      # read_only - (optional) is a type of bool
                      read_only = volume_mount.value["read_only"]
                      # sub_path - (optional) is a type of string
                      sub_path = volume_mount.value["sub_path"]
                    }
                  }

                }
              }

              dynamic "dns_config" {
                for_each = spec.value.dns_config
                content {
                  # nameservers - (optional) is a type of list of string
                  nameservers = dns_config.value["nameservers"]
                  # searches - (optional) is a type of list of string
                  searches = dns_config.value["searches"]

                  dynamic "option" {
                    for_each = dns_config.value.option
                    content {
                      # name - (required) is a type of string
                      name = option.value["name"]
                      # value - (optional) is a type of string
                      value = option.value["value"]
                    }
                  }

                }
              }

              dynamic "host_aliases" {
                for_each = spec.value.host_aliases
                content {
                  # hostnames - (required) is a type of list of string
                  hostnames = host_aliases.value["hostnames"]
                  # ip - (required) is a type of string
                  ip = host_aliases.value["ip"]
                }
              }

              dynamic "image_pull_secrets" {
                for_each = spec.value.image_pull_secrets
                content {
                  # name - (required) is a type of string
                  name = image_pull_secrets.value["name"]
                }
              }

              dynamic "init_container" {
                for_each = spec.value.init_container
                content {
                  # args - (optional) is a type of list of string
                  args = init_container.value["args"]
                  # command - (optional) is a type of list of string
                  command = init_container.value["command"]
                  # image - (optional) is a type of string
                  image = init_container.value["image"]
                  # image_pull_policy - (optional) is a type of string
                  image_pull_policy = init_container.value["image_pull_policy"]
                  # name - (required) is a type of string
                  name = init_container.value["name"]
                  # stdin - (optional) is a type of bool
                  stdin = init_container.value["stdin"]
                  # stdin_once - (optional) is a type of bool
                  stdin_once = init_container.value["stdin_once"]
                  # termination_message_path - (optional) is a type of string
                  termination_message_path = init_container.value["termination_message_path"]
                  # termination_message_policy - (optional) is a type of string
                  termination_message_policy = init_container.value["termination_message_policy"]
                  # tty - (optional) is a type of bool
                  tty = init_container.value["tty"]
                  # working_dir - (optional) is a type of string
                  working_dir = init_container.value["working_dir"]

                  dynamic "env" {
                    for_each = init_container.value.env
                    content {
                      # name - (required) is a type of string
                      name = env.value["name"]
                      # value - (optional) is a type of string
                      value = env.value["value"]

                      dynamic "value_from" {
                        for_each = env.value.value_from
                        content {

                          dynamic "config_map_key_ref" {
                            for_each = value_from.value.config_map_key_ref
                            content {
                              # key - (optional) is a type of string
                              key = config_map_key_ref.value["key"]
                              # name - (optional) is a type of string
                              name = config_map_key_ref.value["name"]
                              # optional - (optional) is a type of bool
                              optional = config_map_key_ref.value["optional"]
                            }
                          }

                          dynamic "field_ref" {
                            for_each = value_from.value.field_ref
                            content {
                              # api_version - (optional) is a type of string
                              api_version = field_ref.value["api_version"]
                              # field_path - (optional) is a type of string
                              field_path = field_ref.value["field_path"]
                            }
                          }

                          dynamic "resource_field_ref" {
                            for_each = value_from.value.resource_field_ref
                            content {
                              # container_name - (optional) is a type of string
                              container_name = resource_field_ref.value["container_name"]
                              # divisor - (optional) is a type of string
                              divisor = resource_field_ref.value["divisor"]
                              # resource - (required) is a type of string
                              resource = resource_field_ref.value["resource"]
                            }
                          }

                          dynamic "secret_key_ref" {
                            for_each = value_from.value.secret_key_ref
                            content {
                              # key - (optional) is a type of string
                              key = secret_key_ref.value["key"]
                              # name - (optional) is a type of string
                              name = secret_key_ref.value["name"]
                              # optional - (optional) is a type of bool
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
                      # prefix - (optional) is a type of string
                      prefix = env_from.value["prefix"]

                      dynamic "config_map_ref" {
                        for_each = env_from.value.config_map_ref
                        content {
                          # name - (required) is a type of string
                          name = config_map_ref.value["name"]
                          # optional - (optional) is a type of bool
                          optional = config_map_ref.value["optional"]
                        }
                      }

                      dynamic "secret_ref" {
                        for_each = env_from.value.secret_ref
                        content {
                          # name - (required) is a type of string
                          name = secret_ref.value["name"]
                          # optional - (optional) is a type of bool
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
                              # command - (optional) is a type of list of string
                              command = exec.value["command"]
                            }
                          }

                          dynamic "http_get" {
                            for_each = post_start.value.http_get
                            content {
                              # host - (optional) is a type of string
                              host = http_get.value["host"]
                              # path - (optional) is a type of string
                              path = http_get.value["path"]
                              # port - (optional) is a type of string
                              port = http_get.value["port"]
                              # scheme - (optional) is a type of string
                              scheme = http_get.value["scheme"]

                              dynamic "http_header" {
                                for_each = http_get.value.http_header
                                content {
                                  # name - (optional) is a type of string
                                  name = http_header.value["name"]
                                  # value - (optional) is a type of string
                                  value = http_header.value["value"]
                                }
                              }

                            }
                          }

                          dynamic "tcp_socket" {
                            for_each = post_start.value.tcp_socket
                            content {
                              # port - (required) is a type of string
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
                              # command - (optional) is a type of list of string
                              command = exec.value["command"]
                            }
                          }

                          dynamic "http_get" {
                            for_each = pre_stop.value.http_get
                            content {
                              # host - (optional) is a type of string
                              host = http_get.value["host"]
                              # path - (optional) is a type of string
                              path = http_get.value["path"]
                              # port - (optional) is a type of string
                              port = http_get.value["port"]
                              # scheme - (optional) is a type of string
                              scheme = http_get.value["scheme"]

                              dynamic "http_header" {
                                for_each = http_get.value.http_header
                                content {
                                  # name - (optional) is a type of string
                                  name = http_header.value["name"]
                                  # value - (optional) is a type of string
                                  value = http_header.value["value"]
                                }
                              }

                            }
                          }

                          dynamic "tcp_socket" {
                            for_each = pre_stop.value.tcp_socket
                            content {
                              # port - (required) is a type of string
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
                      # failure_threshold - (optional) is a type of number
                      failure_threshold = liveness_probe.value["failure_threshold"]
                      # initial_delay_seconds - (optional) is a type of number
                      initial_delay_seconds = liveness_probe.value["initial_delay_seconds"]
                      # period_seconds - (optional) is a type of number
                      period_seconds = liveness_probe.value["period_seconds"]
                      # success_threshold - (optional) is a type of number
                      success_threshold = liveness_probe.value["success_threshold"]
                      # timeout_seconds - (optional) is a type of number
                      timeout_seconds = liveness_probe.value["timeout_seconds"]

                      dynamic "exec" {
                        for_each = liveness_probe.value.exec
                        content {
                          # command - (optional) is a type of list of string
                          command = exec.value["command"]
                        }
                      }

                      dynamic "http_get" {
                        for_each = liveness_probe.value.http_get
                        content {
                          # host - (optional) is a type of string
                          host = http_get.value["host"]
                          # path - (optional) is a type of string
                          path = http_get.value["path"]
                          # port - (optional) is a type of string
                          port = http_get.value["port"]
                          # scheme - (optional) is a type of string
                          scheme = http_get.value["scheme"]

                          dynamic "http_header" {
                            for_each = http_get.value.http_header
                            content {
                              # name - (optional) is a type of string
                              name = http_header.value["name"]
                              # value - (optional) is a type of string
                              value = http_header.value["value"]
                            }
                          }

                        }
                      }

                      dynamic "tcp_socket" {
                        for_each = liveness_probe.value.tcp_socket
                        content {
                          # port - (required) is a type of string
                          port = tcp_socket.value["port"]
                        }
                      }

                    }
                  }

                  dynamic "port" {
                    for_each = init_container.value.port
                    content {
                      # container_port - (required) is a type of number
                      container_port = port.value["container_port"]
                      # host_ip - (optional) is a type of string
                      host_ip = port.value["host_ip"]
                      # host_port - (optional) is a type of number
                      host_port = port.value["host_port"]
                      # name - (optional) is a type of string
                      name = port.value["name"]
                      # protocol - (optional) is a type of string
                      protocol = port.value["protocol"]
                    }
                  }

                  dynamic "readiness_probe" {
                    for_each = init_container.value.readiness_probe
                    content {
                      # failure_threshold - (optional) is a type of number
                      failure_threshold = readiness_probe.value["failure_threshold"]
                      # initial_delay_seconds - (optional) is a type of number
                      initial_delay_seconds = readiness_probe.value["initial_delay_seconds"]
                      # period_seconds - (optional) is a type of number
                      period_seconds = readiness_probe.value["period_seconds"]
                      # success_threshold - (optional) is a type of number
                      success_threshold = readiness_probe.value["success_threshold"]
                      # timeout_seconds - (optional) is a type of number
                      timeout_seconds = readiness_probe.value["timeout_seconds"]

                      dynamic "exec" {
                        for_each = readiness_probe.value.exec
                        content {
                          # command - (optional) is a type of list of string
                          command = exec.value["command"]
                        }
                      }

                      dynamic "http_get" {
                        for_each = readiness_probe.value.http_get
                        content {
                          # host - (optional) is a type of string
                          host = http_get.value["host"]
                          # path - (optional) is a type of string
                          path = http_get.value["path"]
                          # port - (optional) is a type of string
                          port = http_get.value["port"]
                          # scheme - (optional) is a type of string
                          scheme = http_get.value["scheme"]

                          dynamic "http_header" {
                            for_each = http_get.value.http_header
                            content {
                              # name - (optional) is a type of string
                              name = http_header.value["name"]
                              # value - (optional) is a type of string
                              value = http_header.value["value"]
                            }
                          }

                        }
                      }

                      dynamic "tcp_socket" {
                        for_each = readiness_probe.value.tcp_socket
                        content {
                          # port - (required) is a type of string
                          port = tcp_socket.value["port"]
                        }
                      }

                    }
                  }

                  dynamic "resources" {
                    for_each = init_container.value.resources
                    content {
                      # limits - (optional) is a type of map of string
                      limits = resources.value["limits"]
                      # requests - (optional) is a type of map of string
                      requests = resources.value["requests"]
                    }
                  }

                  dynamic "security_context" {
                    for_each = init_container.value.security_context
                    content {
                      # allow_privilege_escalation - (optional) is a type of bool
                      allow_privilege_escalation = security_context.value["allow_privilege_escalation"]
                      # privileged - (optional) is a type of bool
                      privileged = security_context.value["privileged"]
                      # read_only_root_filesystem - (optional) is a type of bool
                      read_only_root_filesystem = security_context.value["read_only_root_filesystem"]
                      # run_as_group - (optional) is a type of string
                      run_as_group = security_context.value["run_as_group"]
                      # run_as_non_root - (optional) is a type of bool
                      run_as_non_root = security_context.value["run_as_non_root"]
                      # run_as_user - (optional) is a type of string
                      run_as_user = security_context.value["run_as_user"]

                      dynamic "capabilities" {
                        for_each = security_context.value.capabilities
                        content {
                          # add - (optional) is a type of list of string
                          add = capabilities.value["add"]
                          # drop - (optional) is a type of list of string
                          drop = capabilities.value["drop"]
                        }
                      }

                      dynamic "se_linux_options" {
                        for_each = security_context.value.se_linux_options
                        content {
                          # level - (optional) is a type of string
                          level = se_linux_options.value["level"]
                          # role - (optional) is a type of string
                          role = se_linux_options.value["role"]
                          # type - (optional) is a type of string
                          type = se_linux_options.value["type"]
                          # user - (optional) is a type of string
                          user = se_linux_options.value["user"]
                        }
                      }

                    }
                  }

                  dynamic "startup_probe" {
                    for_each = init_container.value.startup_probe
                    content {
                      # failure_threshold - (optional) is a type of number
                      failure_threshold = startup_probe.value["failure_threshold"]
                      # initial_delay_seconds - (optional) is a type of number
                      initial_delay_seconds = startup_probe.value["initial_delay_seconds"]
                      # period_seconds - (optional) is a type of number
                      period_seconds = startup_probe.value["period_seconds"]
                      # success_threshold - (optional) is a type of number
                      success_threshold = startup_probe.value["success_threshold"]
                      # timeout_seconds - (optional) is a type of number
                      timeout_seconds = startup_probe.value["timeout_seconds"]

                      dynamic "exec" {
                        for_each = startup_probe.value.exec
                        content {
                          # command - (optional) is a type of list of string
                          command = exec.value["command"]
                        }
                      }

                      dynamic "http_get" {
                        for_each = startup_probe.value.http_get
                        content {
                          # host - (optional) is a type of string
                          host = http_get.value["host"]
                          # path - (optional) is a type of string
                          path = http_get.value["path"]
                          # port - (optional) is a type of string
                          port = http_get.value["port"]
                          # scheme - (optional) is a type of string
                          scheme = http_get.value["scheme"]

                          dynamic "http_header" {
                            for_each = http_get.value.http_header
                            content {
                              # name - (optional) is a type of string
                              name = http_header.value["name"]
                              # value - (optional) is a type of string
                              value = http_header.value["value"]
                            }
                          }

                        }
                      }

                      dynamic "tcp_socket" {
                        for_each = startup_probe.value.tcp_socket
                        content {
                          # port - (required) is a type of string
                          port = tcp_socket.value["port"]
                        }
                      }

                    }
                  }

                  dynamic "volume_mount" {
                    for_each = init_container.value.volume_mount
                    content {
                      # mount_path - (required) is a type of string
                      mount_path = volume_mount.value["mount_path"]
                      # mount_propagation - (optional) is a type of string
                      mount_propagation = volume_mount.value["mount_propagation"]
                      # name - (required) is a type of string
                      name = volume_mount.value["name"]
                      # read_only - (optional) is a type of bool
                      read_only = volume_mount.value["read_only"]
                      # sub_path - (optional) is a type of string
                      sub_path = volume_mount.value["sub_path"]
                    }
                  }

                }
              }

              dynamic "readiness_gate" {
                for_each = spec.value.readiness_gate
                content {
                  # condition_type - (required) is a type of string
                  condition_type = readiness_gate.value["condition_type"]
                }
              }

              dynamic "security_context" {
                for_each = spec.value.security_context
                content {
                  # fs_group - (optional) is a type of string
                  fs_group = security_context.value["fs_group"]
                  # run_as_group - (optional) is a type of string
                  run_as_group = security_context.value["run_as_group"]
                  # run_as_non_root - (optional) is a type of bool
                  run_as_non_root = security_context.value["run_as_non_root"]
                  # run_as_user - (optional) is a type of string
                  run_as_user = security_context.value["run_as_user"]
                  # supplemental_groups - (optional) is a type of set of number
                  supplemental_groups = security_context.value["supplemental_groups"]

                  dynamic "se_linux_options" {
                    for_each = security_context.value.se_linux_options
                    content {
                      # level - (optional) is a type of string
                      level = se_linux_options.value["level"]
                      # role - (optional) is a type of string
                      role = se_linux_options.value["role"]
                      # type - (optional) is a type of string
                      type = se_linux_options.value["type"]
                      # user - (optional) is a type of string
                      user = se_linux_options.value["user"]
                    }
                  }

                  dynamic "sysctl" {
                    for_each = security_context.value.sysctl
                    content {
                      # name - (required) is a type of string
                      name = sysctl.value["name"]
                      # value - (required) is a type of string
                      value = sysctl.value["value"]
                    }
                  }

                }
              }

              dynamic "toleration" {
                for_each = spec.value.toleration
                content {
                  # effect - (optional) is a type of string
                  effect = toleration.value["effect"]
                  # key - (optional) is a type of string
                  key = toleration.value["key"]
                  # operator - (optional) is a type of string
                  operator = toleration.value["operator"]
                  # toleration_seconds - (optional) is a type of string
                  toleration_seconds = toleration.value["toleration_seconds"]
                  # value - (optional) is a type of string
                  value = toleration.value["value"]
                }
              }

              dynamic "topology_spread_constraint" {
                for_each = spec.value.topology_spread_constraint
                content {
                  # max_skew - (optional) is a type of number
                  max_skew = topology_spread_constraint.value["max_skew"]
                  # topology_key - (optional) is a type of string
                  topology_key = topology_spread_constraint.value["topology_key"]
                  # when_unsatisfiable - (optional) is a type of string
                  when_unsatisfiable = topology_spread_constraint.value["when_unsatisfiable"]

                  dynamic "label_selector" {
                    for_each = topology_spread_constraint.value.label_selector
                    content {
                      # match_labels - (optional) is a type of map of string
                      match_labels = label_selector.value["match_labels"]

                      dynamic "match_expressions" {
                        for_each = label_selector.value.match_expressions
                        content {
                          # key - (optional) is a type of string
                          key = match_expressions.value["key"]
                          # operator - (optional) is a type of string
                          operator = match_expressions.value["operator"]
                          # values - (optional) is a type of set of string
                          values = match_expressions.value["values"]
                        }
                      }

                    }
                  }

                }
              }

              dynamic "volume" {
                for_each = spec.value.volume
                content {
                  # name - (optional) is a type of string
                  name = volume.value["name"]

                  dynamic "aws_elastic_block_store" {
                    for_each = volume.value.aws_elastic_block_store
                    content {
                      # fs_type - (optional) is a type of string
                      fs_type = aws_elastic_block_store.value["fs_type"]
                      # partition - (optional) is a type of number
                      partition = aws_elastic_block_store.value["partition"]
                      # read_only - (optional) is a type of bool
                      read_only = aws_elastic_block_store.value["read_only"]
                      # volume_id - (required) is a type of string
                      volume_id = aws_elastic_block_store.value["volume_id"]
                    }
                  }

                  dynamic "azure_disk" {
                    for_each = volume.value.azure_disk
                    content {
                      # caching_mode - (required) is a type of string
                      caching_mode = azure_disk.value["caching_mode"]
                      # data_disk_uri - (required) is a type of string
                      data_disk_uri = azure_disk.value["data_disk_uri"]
                      # disk_name - (required) is a type of string
                      disk_name = azure_disk.value["disk_name"]
                      # fs_type - (optional) is a type of string
                      fs_type = azure_disk.value["fs_type"]
                      # kind - (optional) is a type of string
                      kind = azure_disk.value["kind"]
                      # read_only - (optional) is a type of bool
                      read_only = azure_disk.value["read_only"]
                    }
                  }

                  dynamic "azure_file" {
                    for_each = volume.value.azure_file
                    content {
                      # read_only - (optional) is a type of bool
                      read_only = azure_file.value["read_only"]
                      # secret_name - (required) is a type of string
                      secret_name = azure_file.value["secret_name"]
                      # share_name - (required) is a type of string
                      share_name = azure_file.value["share_name"]
                    }
                  }

                  dynamic "ceph_fs" {
                    for_each = volume.value.ceph_fs
                    content {
                      # monitors - (required) is a type of set of string
                      monitors = ceph_fs.value["monitors"]
                      # path - (optional) is a type of string
                      path = ceph_fs.value["path"]
                      # read_only - (optional) is a type of bool
                      read_only = ceph_fs.value["read_only"]
                      # secret_file - (optional) is a type of string
                      secret_file = ceph_fs.value["secret_file"]
                      # user - (optional) is a type of string
                      user = ceph_fs.value["user"]

                      dynamic "secret_ref" {
                        for_each = ceph_fs.value.secret_ref
                        content {
                          # name - (optional) is a type of string
                          name = secret_ref.value["name"]
                          # namespace - (optional) is a type of string
                          namespace = secret_ref.value["namespace"]
                        }
                      }

                    }
                  }

                  dynamic "cinder" {
                    for_each = volume.value.cinder
                    content {
                      # fs_type - (optional) is a type of string
                      fs_type = cinder.value["fs_type"]
                      # read_only - (optional) is a type of bool
                      read_only = cinder.value["read_only"]
                      # volume_id - (required) is a type of string
                      volume_id = cinder.value["volume_id"]
                    }
                  }

                  dynamic "config_map" {
                    for_each = volume.value.config_map
                    content {
                      # default_mode - (optional) is a type of string
                      default_mode = config_map.value["default_mode"]
                      # name - (optional) is a type of string
                      name = config_map.value["name"]
                      # optional - (optional) is a type of bool
                      optional = config_map.value["optional"]

                      dynamic "items" {
                        for_each = config_map.value.items
                        content {
                          # key - (optional) is a type of string
                          key = items.value["key"]
                          # mode - (optional) is a type of string
                          mode = items.value["mode"]
                          # path - (optional) is a type of string
                          path = items.value["path"]
                        }
                      }

                    }
                  }

                  dynamic "csi" {
                    for_each = volume.value.csi
                    content {
                      # driver - (required) is a type of string
                      driver = csi.value["driver"]
                      # fs_type - (optional) is a type of string
                      fs_type = csi.value["fs_type"]
                      # read_only - (optional) is a type of bool
                      read_only = csi.value["read_only"]
                      # volume_attributes - (optional) is a type of map of string
                      volume_attributes = csi.value["volume_attributes"]
                      # volume_handle - (required) is a type of string
                      volume_handle = csi.value["volume_handle"]

                      dynamic "controller_expand_secret_ref" {
                        for_each = csi.value.controller_expand_secret_ref
                        content {
                          # name - (optional) is a type of string
                          name = controller_expand_secret_ref.value["name"]
                          # namespace - (optional) is a type of string
                          namespace = controller_expand_secret_ref.value["namespace"]
                        }
                      }

                      dynamic "controller_publish_secret_ref" {
                        for_each = csi.value.controller_publish_secret_ref
                        content {
                          # name - (optional) is a type of string
                          name = controller_publish_secret_ref.value["name"]
                          # namespace - (optional) is a type of string
                          namespace = controller_publish_secret_ref.value["namespace"]
                        }
                      }

                      dynamic "node_publish_secret_ref" {
                        for_each = csi.value.node_publish_secret_ref
                        content {
                          # name - (optional) is a type of string
                          name = node_publish_secret_ref.value["name"]
                          # namespace - (optional) is a type of string
                          namespace = node_publish_secret_ref.value["namespace"]
                        }
                      }

                      dynamic "node_stage_secret_ref" {
                        for_each = csi.value.node_stage_secret_ref
                        content {
                          # name - (optional) is a type of string
                          name = node_stage_secret_ref.value["name"]
                          # namespace - (optional) is a type of string
                          namespace = node_stage_secret_ref.value["namespace"]
                        }
                      }

                    }
                  }

                  dynamic "downward_api" {
                    for_each = volume.value.downward_api
                    content {
                      # default_mode - (optional) is a type of string
                      default_mode = downward_api.value["default_mode"]

                      dynamic "items" {
                        for_each = downward_api.value.items
                        content {
                          # mode - (optional) is a type of string
                          mode = items.value["mode"]
                          # path - (required) is a type of string
                          path = items.value["path"]

                          dynamic "field_ref" {
                            for_each = items.value.field_ref
                            content {
                              # api_version - (optional) is a type of string
                              api_version = field_ref.value["api_version"]
                              # field_path - (optional) is a type of string
                              field_path = field_ref.value["field_path"]
                            }
                          }

                          dynamic "resource_field_ref" {
                            for_each = items.value.resource_field_ref
                            content {
                              # container_name - (required) is a type of string
                              container_name = resource_field_ref.value["container_name"]
                              # divisor - (optional) is a type of string
                              divisor = resource_field_ref.value["divisor"]
                              # resource - (required) is a type of string
                              resource = resource_field_ref.value["resource"]
                            }
                          }

                        }
                      }

                    }
                  }

                  dynamic "empty_dir" {
                    for_each = volume.value.empty_dir
                    content {
                      # medium - (optional) is a type of string
                      medium = empty_dir.value["medium"]
                      # size_limit - (optional) is a type of string
                      size_limit = empty_dir.value["size_limit"]
                    }
                  }

                  dynamic "fc" {
                    for_each = volume.value.fc
                    content {
                      # fs_type - (optional) is a type of string
                      fs_type = fc.value["fs_type"]
                      # lun - (required) is a type of number
                      lun = fc.value["lun"]
                      # read_only - (optional) is a type of bool
                      read_only = fc.value["read_only"]
                      # target_ww_ns - (required) is a type of set of string
                      target_ww_ns = fc.value["target_ww_ns"]
                    }
                  }

                  dynamic "flex_volume" {
                    for_each = volume.value.flex_volume
                    content {
                      # driver - (required) is a type of string
                      driver = flex_volume.value["driver"]
                      # fs_type - (optional) is a type of string
                      fs_type = flex_volume.value["fs_type"]
                      # options - (optional) is a type of map of string
                      options = flex_volume.value["options"]
                      # read_only - (optional) is a type of bool
                      read_only = flex_volume.value["read_only"]

                      dynamic "secret_ref" {
                        for_each = flex_volume.value.secret_ref
                        content {
                          # name - (optional) is a type of string
                          name = secret_ref.value["name"]
                          # namespace - (optional) is a type of string
                          namespace = secret_ref.value["namespace"]
                        }
                      }

                    }
                  }

                  dynamic "flocker" {
                    for_each = volume.value.flocker
                    content {
                      # dataset_name - (optional) is a type of string
                      dataset_name = flocker.value["dataset_name"]
                      # dataset_uuid - (optional) is a type of string
                      dataset_uuid = flocker.value["dataset_uuid"]
                    }
                  }

                  dynamic "gce_persistent_disk" {
                    for_each = volume.value.gce_persistent_disk
                    content {
                      # fs_type - (optional) is a type of string
                      fs_type = gce_persistent_disk.value["fs_type"]
                      # partition - (optional) is a type of number
                      partition = gce_persistent_disk.value["partition"]
                      # pd_name - (required) is a type of string
                      pd_name = gce_persistent_disk.value["pd_name"]
                      # read_only - (optional) is a type of bool
                      read_only = gce_persistent_disk.value["read_only"]
                    }
                  }

                  dynamic "git_repo" {
                    for_each = volume.value.git_repo
                    content {
                      # directory - (optional) is a type of string
                      directory = git_repo.value["directory"]
                      # repository - (optional) is a type of string
                      repository = git_repo.value["repository"]
                      # revision - (optional) is a type of string
                      revision = git_repo.value["revision"]
                    }
                  }

                  dynamic "glusterfs" {
                    for_each = volume.value.glusterfs
                    content {
                      # endpoints_name - (required) is a type of string
                      endpoints_name = glusterfs.value["endpoints_name"]
                      # path - (required) is a type of string
                      path = glusterfs.value["path"]
                      # read_only - (optional) is a type of bool
                      read_only = glusterfs.value["read_only"]
                    }
                  }

                  dynamic "host_path" {
                    for_each = volume.value.host_path
                    content {
                      # path - (optional) is a type of string
                      path = host_path.value["path"]
                      # type - (optional) is a type of string
                      type = host_path.value["type"]
                    }
                  }

                  dynamic "iscsi" {
                    for_each = volume.value.iscsi
                    content {
                      # fs_type - (optional) is a type of string
                      fs_type = iscsi.value["fs_type"]
                      # iqn - (required) is a type of string
                      iqn = iscsi.value["iqn"]
                      # iscsi_interface - (optional) is a type of string
                      iscsi_interface = iscsi.value["iscsi_interface"]
                      # lun - (optional) is a type of number
                      lun = iscsi.value["lun"]
                      # read_only - (optional) is a type of bool
                      read_only = iscsi.value["read_only"]
                      # target_portal - (required) is a type of string
                      target_portal = iscsi.value["target_portal"]
                    }
                  }

                  dynamic "local" {
                    for_each = volume.value.local
                    content {
                      # path - (optional) is a type of string
                      path = local.value["path"]
                    }
                  }

                  dynamic "nfs" {
                    for_each = volume.value.nfs
                    content {
                      # path - (required) is a type of string
                      path = nfs.value["path"]
                      # read_only - (optional) is a type of bool
                      read_only = nfs.value["read_only"]
                      # server - (required) is a type of string
                      server = nfs.value["server"]
                    }
                  }

                  dynamic "persistent_volume_claim" {
                    for_each = volume.value.persistent_volume_claim
                    content {
                      # claim_name - (optional) is a type of string
                      claim_name = persistent_volume_claim.value["claim_name"]
                      # read_only - (optional) is a type of bool
                      read_only = persistent_volume_claim.value["read_only"]
                    }
                  }

                  dynamic "photon_persistent_disk" {
                    for_each = volume.value.photon_persistent_disk
                    content {
                      # fs_type - (optional) is a type of string
                      fs_type = photon_persistent_disk.value["fs_type"]
                      # pd_id - (required) is a type of string
                      pd_id = photon_persistent_disk.value["pd_id"]
                    }
                  }

                  dynamic "projected" {
                    for_each = volume.value.projected
                    content {
                      # default_mode - (optional) is a type of string
                      default_mode = projected.value["default_mode"]

                      dynamic "sources" {
                        for_each = projected.value.sources
                        content {

                          dynamic "config_map" {
                            for_each = sources.value.config_map
                            content {
                              # name - (optional) is a type of string
                              name = config_map.value["name"]
                              # optional - (optional) is a type of bool
                              optional = config_map.value["optional"]

                              dynamic "items" {
                                for_each = config_map.value.items
                                content {
                                  # key - (optional) is a type of string
                                  key = items.value["key"]
                                  # mode - (optional) is a type of string
                                  mode = items.value["mode"]
                                  # path - (optional) is a type of string
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
                                  # mode - (optional) is a type of string
                                  mode = items.value["mode"]
                                  # path - (required) is a type of string
                                  path = items.value["path"]

                                  dynamic "field_ref" {
                                    for_each = items.value.field_ref
                                    content {
                                      # api_version - (optional) is a type of string
                                      api_version = field_ref.value["api_version"]
                                      # field_path - (optional) is a type of string
                                      field_path = field_ref.value["field_path"]
                                    }
                                  }

                                  dynamic "resource_field_ref" {
                                    for_each = items.value.resource_field_ref
                                    content {
                                      # container_name - (required) is a type of string
                                      container_name = resource_field_ref.value["container_name"]
                                      # divisor - (optional) is a type of string
                                      divisor = resource_field_ref.value["divisor"]
                                      # resource - (required) is a type of string
                                      resource = resource_field_ref.value["resource"]
                                    }
                                  }

                                }
                              }

                            }
                          }

                          dynamic "secret" {
                            for_each = sources.value.secret
                            content {
                              # name - (optional) is a type of string
                              name = secret.value["name"]
                              # optional - (optional) is a type of bool
                              optional = secret.value["optional"]

                              dynamic "items" {
                                for_each = secret.value.items
                                content {
                                  # key - (optional) is a type of string
                                  key = items.value["key"]
                                  # mode - (optional) is a type of string
                                  mode = items.value["mode"]
                                  # path - (optional) is a type of string
                                  path = items.value["path"]
                                }
                              }

                            }
                          }

                          dynamic "service_account_token" {
                            for_each = sources.value.service_account_token
                            content {
                              # audience - (optional) is a type of string
                              audience = service_account_token.value["audience"]
                              # expiration_seconds - (optional) is a type of number
                              expiration_seconds = service_account_token.value["expiration_seconds"]
                              # path - (required) is a type of string
                              path = service_account_token.value["path"]
                            }
                          }

                        }
                      }

                    }
                  }

                  dynamic "quobyte" {
                    for_each = volume.value.quobyte
                    content {
                      # group - (optional) is a type of string
                      group = quobyte.value["group"]
                      # read_only - (optional) is a type of bool
                      read_only = quobyte.value["read_only"]
                      # registry - (required) is a type of string
                      registry = quobyte.value["registry"]
                      # user - (optional) is a type of string
                      user = quobyte.value["user"]
                      # volume - (required) is a type of string
                      volume = quobyte.value["volume"]
                    }
                  }

                  dynamic "rbd" {
                    for_each = volume.value.rbd
                    content {
                      # ceph_monitors - (required) is a type of set of string
                      ceph_monitors = rbd.value["ceph_monitors"]
                      # fs_type - (optional) is a type of string
                      fs_type = rbd.value["fs_type"]
                      # keyring - (optional) is a type of string
                      keyring = rbd.value["keyring"]
                      # rados_user - (optional) is a type of string
                      rados_user = rbd.value["rados_user"]
                      # rbd_image - (required) is a type of string
                      rbd_image = rbd.value["rbd_image"]
                      # rbd_pool - (optional) is a type of string
                      rbd_pool = rbd.value["rbd_pool"]
                      # read_only - (optional) is a type of bool
                      read_only = rbd.value["read_only"]

                      dynamic "secret_ref" {
                        for_each = rbd.value.secret_ref
                        content {
                          # name - (optional) is a type of string
                          name = secret_ref.value["name"]
                          # namespace - (optional) is a type of string
                          namespace = secret_ref.value["namespace"]
                        }
                      }

                    }
                  }

                  dynamic "secret" {
                    for_each = volume.value.secret
                    content {
                      # default_mode - (optional) is a type of string
                      default_mode = secret.value["default_mode"]
                      # optional - (optional) is a type of bool
                      optional = secret.value["optional"]
                      # secret_name - (optional) is a type of string
                      secret_name = secret.value["secret_name"]

                      dynamic "items" {
                        for_each = secret.value.items
                        content {
                          # key - (optional) is a type of string
                          key = items.value["key"]
                          # mode - (optional) is a type of string
                          mode = items.value["mode"]
                          # path - (optional) is a type of string
                          path = items.value["path"]
                        }
                      }

                    }
                  }

                  dynamic "vsphere_volume" {
                    for_each = volume.value.vsphere_volume
                    content {
                      # fs_type - (optional) is a type of string
                      fs_type = vsphere_volume.value["fs_type"]
                      # volume_path - (required) is a type of string
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

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = kubernetes_job.this.id
}

output "this" {
  value = kubernetes_job.this
}
```

[top](#index)