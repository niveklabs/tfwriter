# rancher2_cluster_template

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_cluster_template" {
  source = "./modules/rancher2/r/rancher2_cluster_template"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # description - (optional) is a type of string
  description = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null

  members = [{
    access_type        = null
    group_principal_id = null
    user_principal_id  = null
  }]

  template_revisions = [{
    annotations = {}
    cluster_config = [{
      cluster_auth_endpoint = [{
        ca_certs = null
        enabled  = null
        fqdn     = null
      }]
      default_cluster_role_for_project_members = null
      default_pod_security_policy_template_id  = null
      desired_agent_image                      = null
      desired_auth_image                       = null
      docker_root_dir                          = null
      enable_cluster_alerting                  = null
      enable_cluster_monitoring                = null
      enable_network_policy                    = null
      rke_config = [{
        addon_job_timeout = null
        addons            = null
        addons_include    = []
        authentication = [{
          sans     = []
          strategy = null
        }]
        authorization = [{
          mode    = null
          options = {}
        }]
        bastion_host = [{
          address        = null
          port           = null
          ssh_agent_auth = null
          ssh_key        = null
          ssh_key_path   = null
          user           = null
        }]
        cloud_provider = [{
          aws_cloud_provider = [{
            global = [{
              disable_security_group_ingress = null
              disable_strict_zone_check      = null
              elb_security_group             = null
              kubernetes_cluster_id          = null
              kubernetes_cluster_tag         = null
              role_arn                       = null
              route_table_id                 = null
              subnet_id                      = null
              vpc                            = null
              zone                           = null
            }]
            service_override = [{
              region         = null
              service        = null
              signing_method = null
              signing_name   = null
              signing_region = null
              url            = null
            }]
          }]
          azure_cloud_provider = [{
            aad_client_cert_password         = null
            aad_client_cert_path             = null
            aad_client_id                    = null
            aad_client_secret                = null
            cloud                            = null
            cloud_provider_backoff           = null
            cloud_provider_backoff_duration  = null
            cloud_provider_backoff_exponent  = null
            cloud_provider_backoff_jitter    = null
            cloud_provider_backoff_retries   = null
            cloud_provider_rate_limit        = null
            cloud_provider_rate_limit_bucket = null
            cloud_provider_rate_limit_qps    = null
            load_balancer_sku                = null
            location                         = null
            maximum_load_balancer_rule_count = null
            primary_availability_set_name    = null
            primary_scale_set_name           = null
            resource_group                   = null
            route_table_name                 = null
            security_group_name              = null
            subnet_name                      = null
            subscription_id                  = null
            tenant_id                        = null
            use_instance_metadata            = null
            use_managed_identity_extension   = null
            vm_type                          = null
            vnet_name                        = null
            vnet_resource_group              = null
          }]
          custom_cloud_provider = null
          name                  = null
          openstack_cloud_provider = [{
            block_storage = [{
              bs_version        = null
              ignore_volume_az  = null
              trust_device_path = null
            }]
            global = [{
              auth_url    = null
              ca_file     = null
              domain_id   = null
              domain_name = null
              password    = null
              region      = null
              tenant_id   = null
              tenant_name = null
              trust_id    = null
              username    = null
            }]
            load_balancer = [{
              create_monitor         = null
              floating_network_id    = null
              lb_method              = null
              lb_provider            = null
              lb_version             = null
              manage_security_groups = null
              monitor_delay          = null
              monitor_max_retries    = null
              monitor_timeout        = null
              subnet_id              = null
              use_octavia            = null
            }]
            metadata = [{
              request_timeout = null
              search_order    = null
            }]
            route = [{
              router_id = null
            }]
          }]
          vsphere_cloud_provider = [{
            disk = [{
              scsi_controller_type = null
            }]
            global = [{
              datacenters          = null
              insecure_flag        = null
              password             = null
              port                 = null
              soap_roundtrip_count = null
              user                 = null
            }]
            network = [{
              public_network = null
            }]
            virtual_center = [{
              datacenters          = null
              name                 = null
              password             = null
              port                 = null
              soap_roundtrip_count = null
              user                 = null
            }]
            workspace = [{
              datacenter        = null
              default_datastore = null
              folder            = null
              resourcepool_path = null
              server            = null
            }]
          }]
        }]
        dns = [{
          linear_autoscaler_params = [{
            cores_per_replica            = null
            max                          = null
            min                          = null
            nodes_per_replica            = null
            prevent_single_point_failure = null
          }]
          node_selector = {}
          nodelocal = [{
            ip_address    = null
            node_selector = {}
          }]
          provider      = null
          reverse_cidrs = []
          update_strategy = [{
            rolling_update = [{
              max_surge       = null
              max_unavailable = null
            }]
            strategy = null
          }]
          upstream_nameservers = []
        }]
        ignore_docker_version = null
        ingress = [{
          dns_policy    = null
          extra_args    = {}
          node_selector = {}
          options       = {}
          provider      = null
        }]
        kubernetes_version = null
        monitoring = [{
          node_selector = {}
          options       = {}
          provider      = null
          replicas      = null
          update_strategy = [{
            rolling_update = [{
              max_surge       = null
              max_unavailable = null
            }]
            strategy = null
          }]
        }]
        network = [{
          calico_network_provider = [{
            cloud_provider = null
          }]
          canal_network_provider = [{
            iface = null
          }]
          flannel_network_provider = [{
            iface = null
          }]
          mtu     = null
          options = {}
          plugin  = null
          weave_network_provider = [{
            password = null
          }]
        }]
        nodes = [{
          address           = null
          docker_socket     = null
          hostname_override = null
          internal_address  = null
          labels            = {}
          node_id           = null
          port              = null
          role              = []
          ssh_agent_auth    = null
          ssh_key           = null
          ssh_key_path      = null
          user              = null
        }]
        prefix_path = null
        private_registries = [{
          is_default = null
          password   = null
          url        = null
          user       = null
        }]
        services = [{
          etcd = [{
            backup_config = [{
              enabled        = null
              interval_hours = null
              retention      = null
              s3_backup_config = [{
                access_key  = null
                bucket_name = null
                custom_ca   = null
                endpoint    = null
                folder      = null
                region      = null
                secret_key  = null
              }]
              safe_timestamp = null
              timeout        = null
            }]
            ca_cert       = null
            cert          = null
            creation      = null
            external_urls = []
            extra_args    = {}
            extra_binds   = []
            extra_env     = []
            gid           = null
            image         = null
            key           = null
            path          = null
            retention     = null
            snapshot      = null
            uid           = null
          }]
          kube_api = [{
            admission_configuration = {}
            always_pull_images      = null
            audit_log = [{
              configuration = [{
                format     = null
                max_age    = null
                max_backup = null
                max_size   = null
                path       = null
                policy     = null
              }]
              enabled = null
            }]
            event_rate_limit = [{
              configuration = null
              enabled       = null
            }]
            extra_args          = {}
            extra_binds         = []
            extra_env           = []
            image               = null
            pod_security_policy = null
            secrets_encryption_config = [{
              custom_config = null
              enabled       = null
            }]
            service_cluster_ip_range = null
            service_node_port_range  = null
          }]
          kube_controller = [{
            cluster_cidr             = null
            extra_args               = {}
            extra_binds              = []
            extra_env                = []
            image                    = null
            service_cluster_ip_range = null
          }]
          kubelet = [{
            cluster_dns_server           = null
            cluster_domain               = null
            extra_args                   = {}
            extra_binds                  = []
            extra_env                    = []
            fail_swap_on                 = null
            generate_serving_certificate = null
            image                        = null
            infra_container_image        = null
          }]
          kubeproxy = [{
            extra_args  = {}
            extra_binds = []
            extra_env   = []
            image       = null
          }]
          scheduler = [{
            extra_args  = {}
            extra_binds = []
            extra_env   = []
            image       = null
          }]
        }]
        ssh_agent_auth = null
        ssh_cert_path  = null
        ssh_key_path   = null
        upgrade_strategy = [{
          drain = null
          drain_input = [{
            delete_local_data  = null
            force              = null
            grace_period       = null
            ignore_daemon_sets = null
            timeout            = null
          }]
          max_unavailable_controlplane = null
          max_unavailable_worker       = null
        }]
        win_prefix_path = null
      }]
      scheduled_cluster_scan = [{
        enabled = null
        scan_config = [{
          cis_scan_config = [{
            debug_master               = null
            debug_worker               = null
            override_benchmark_version = null
            override_skip              = []
            profile                    = null
          }]
        }]
        schedule_config = [{
          cron_schedule = null
          retention     = null
        }]
      }]
      windows_prefered_cluster = null
    }]
    cluster_template_id = null
    default             = null
    enabled             = null
    id                  = null
    labels              = {}
    name                = null
    questions = [{
      default  = null
      required = null
      type     = null
      variable = null
    }]
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
variable "annotations" {
  description = "(optional) - Annotations of the resource"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional) - Cluster template description"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Cluster template name"
  type        = string
}

variable "members" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      access_type        = string
      group_principal_id = string
      user_principal_id  = string
    }
  ))
  default = []
}

variable "template_revisions" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      annotations = map(string)
      cluster_config = list(object(
        {
          cluster_auth_endpoint = list(object(
            {
              ca_certs = string
              enabled  = bool
              fqdn     = string
            }
          ))
          default_cluster_role_for_project_members = string
          default_pod_security_policy_template_id  = string
          desired_agent_image                      = string
          desired_auth_image                       = string
          docker_root_dir                          = string
          enable_cluster_alerting                  = bool
          enable_cluster_monitoring                = bool
          enable_network_policy                    = bool
          rke_config = list(object(
            {
              addon_job_timeout = number
              addons            = string
              addons_include    = list(string)
              authentication = list(object(
                {
                  sans     = list(string)
                  strategy = string
                }
              ))
              authorization = list(object(
                {
                  mode    = string
                  options = map(string)
                }
              ))
              bastion_host = list(object(
                {
                  address        = string
                  port           = string
                  ssh_agent_auth = bool
                  ssh_key        = string
                  ssh_key_path   = string
                  user           = string
                }
              ))
              cloud_provider = list(object(
                {
                  aws_cloud_provider = list(object(
                    {
                      global = list(object(
                        {
                          disable_security_group_ingress = bool
                          disable_strict_zone_check      = bool
                          elb_security_group             = string
                          kubernetes_cluster_id          = string
                          kubernetes_cluster_tag         = string
                          role_arn                       = string
                          route_table_id                 = string
                          subnet_id                      = string
                          vpc                            = string
                          zone                           = string
                        }
                      ))
                      service_override = list(object(
                        {
                          region         = string
                          service        = string
                          signing_method = string
                          signing_name   = string
                          signing_region = string
                          url            = string
                        }
                      ))
                    }
                  ))
                  azure_cloud_provider = list(object(
                    {
                      aad_client_cert_password         = string
                      aad_client_cert_path             = string
                      aad_client_id                    = string
                      aad_client_secret                = string
                      cloud                            = string
                      cloud_provider_backoff           = bool
                      cloud_provider_backoff_duration  = number
                      cloud_provider_backoff_exponent  = number
                      cloud_provider_backoff_jitter    = number
                      cloud_provider_backoff_retries   = number
                      cloud_provider_rate_limit        = bool
                      cloud_provider_rate_limit_bucket = number
                      cloud_provider_rate_limit_qps    = number
                      load_balancer_sku                = string
                      location                         = string
                      maximum_load_balancer_rule_count = number
                      primary_availability_set_name    = string
                      primary_scale_set_name           = string
                      resource_group                   = string
                      route_table_name                 = string
                      security_group_name              = string
                      subnet_name                      = string
                      subscription_id                  = string
                      tenant_id                        = string
                      use_instance_metadata            = bool
                      use_managed_identity_extension   = bool
                      vm_type                          = string
                      vnet_name                        = string
                      vnet_resource_group              = string
                    }
                  ))
                  custom_cloud_provider = string
                  name                  = string
                  openstack_cloud_provider = list(object(
                    {
                      block_storage = list(object(
                        {
                          bs_version        = string
                          ignore_volume_az  = bool
                          trust_device_path = bool
                        }
                      ))
                      global = list(object(
                        {
                          auth_url    = string
                          ca_file     = string
                          domain_id   = string
                          domain_name = string
                          password    = string
                          region      = string
                          tenant_id   = string
                          tenant_name = string
                          trust_id    = string
                          username    = string
                        }
                      ))
                      load_balancer = list(object(
                        {
                          create_monitor         = bool
                          floating_network_id    = string
                          lb_method              = string
                          lb_provider            = string
                          lb_version             = string
                          manage_security_groups = bool
                          monitor_delay          = string
                          monitor_max_retries    = number
                          monitor_timeout        = string
                          subnet_id              = string
                          use_octavia            = bool
                        }
                      ))
                      metadata = list(object(
                        {
                          request_timeout = number
                          search_order    = string
                        }
                      ))
                      route = list(object(
                        {
                          router_id = string
                        }
                      ))
                    }
                  ))
                  vsphere_cloud_provider = list(object(
                    {
                      disk = list(object(
                        {
                          scsi_controller_type = string
                        }
                      ))
                      global = list(object(
                        {
                          datacenters          = string
                          insecure_flag        = bool
                          password             = string
                          port                 = string
                          soap_roundtrip_count = number
                          user                 = string
                        }
                      ))
                      network = list(object(
                        {
                          public_network = string
                        }
                      ))
                      virtual_center = list(object(
                        {
                          datacenters          = string
                          name                 = string
                          password             = string
                          port                 = string
                          soap_roundtrip_count = number
                          user                 = string
                        }
                      ))
                      workspace = list(object(
                        {
                          datacenter        = string
                          default_datastore = string
                          folder            = string
                          resourcepool_path = string
                          server            = string
                        }
                      ))
                    }
                  ))
                }
              ))
              dns = list(object(
                {
                  linear_autoscaler_params = list(object(
                    {
                      cores_per_replica            = number
                      max                          = number
                      min                          = number
                      nodes_per_replica            = number
                      prevent_single_point_failure = bool
                    }
                  ))
                  node_selector = map(string)
                  nodelocal = list(object(
                    {
                      ip_address    = string
                      node_selector = map(string)
                    }
                  ))
                  provider      = string
                  reverse_cidrs = list(string)
                  update_strategy = list(object(
                    {
                      rolling_update = list(object(
                        {
                          max_surge       = number
                          max_unavailable = number
                        }
                      ))
                      strategy = string
                    }
                  ))
                  upstream_nameservers = list(string)
                }
              ))
              ignore_docker_version = bool
              ingress = list(object(
                {
                  dns_policy    = string
                  extra_args    = map(string)
                  node_selector = map(string)
                  options       = map(string)
                  provider      = string
                }
              ))
              kubernetes_version = string
              monitoring = list(object(
                {
                  node_selector = map(string)
                  options       = map(string)
                  provider      = string
                  replicas      = number
                  update_strategy = list(object(
                    {
                      rolling_update = list(object(
                        {
                          max_surge       = number
                          max_unavailable = number
                        }
                      ))
                      strategy = string
                    }
                  ))
                }
              ))
              network = list(object(
                {
                  calico_network_provider = list(object(
                    {
                      cloud_provider = string
                    }
                  ))
                  canal_network_provider = list(object(
                    {
                      iface = string
                    }
                  ))
                  flannel_network_provider = list(object(
                    {
                      iface = string
                    }
                  ))
                  mtu     = number
                  options = map(string)
                  plugin  = string
                  weave_network_provider = list(object(
                    {
                      password = string
                    }
                  ))
                }
              ))
              nodes = list(object(
                {
                  address           = string
                  docker_socket     = string
                  hostname_override = string
                  internal_address  = string
                  labels            = map(string)
                  node_id           = string
                  port              = string
                  role              = list(string)
                  ssh_agent_auth    = bool
                  ssh_key           = string
                  ssh_key_path      = string
                  user              = string
                }
              ))
              prefix_path = string
              private_registries = list(object(
                {
                  is_default = bool
                  password   = string
                  url        = string
                  user       = string
                }
              ))
              services = list(object(
                {
                  etcd = list(object(
                    {
                      backup_config = list(object(
                        {
                          enabled        = bool
                          interval_hours = number
                          retention      = number
                          s3_backup_config = list(object(
                            {
                              access_key  = string
                              bucket_name = string
                              custom_ca   = string
                              endpoint    = string
                              folder      = string
                              region      = string
                              secret_key  = string
                            }
                          ))
                          safe_timestamp = bool
                          timeout        = number
                        }
                      ))
                      ca_cert       = string
                      cert          = string
                      creation      = string
                      external_urls = list(string)
                      extra_args    = map(string)
                      extra_binds   = list(string)
                      extra_env     = list(string)
                      gid           = number
                      image         = string
                      key           = string
                      path          = string
                      retention     = string
                      snapshot      = bool
                      uid           = number
                    }
                  ))
                  kube_api = list(object(
                    {
                      admission_configuration = map(string)
                      always_pull_images      = bool
                      audit_log = list(object(
                        {
                          configuration = list(object(
                            {
                              format     = string
                              max_age    = number
                              max_backup = number
                              max_size   = number
                              path       = string
                              policy     = string
                            }
                          ))
                          enabled = bool
                        }
                      ))
                      event_rate_limit = list(object(
                        {
                          configuration = string
                          enabled       = bool
                        }
                      ))
                      extra_args          = map(string)
                      extra_binds         = list(string)
                      extra_env           = list(string)
                      image               = string
                      pod_security_policy = bool
                      secrets_encryption_config = list(object(
                        {
                          custom_config = string
                          enabled       = bool
                        }
                      ))
                      service_cluster_ip_range = string
                      service_node_port_range  = string
                    }
                  ))
                  kube_controller = list(object(
                    {
                      cluster_cidr             = string
                      extra_args               = map(string)
                      extra_binds              = list(string)
                      extra_env                = list(string)
                      image                    = string
                      service_cluster_ip_range = string
                    }
                  ))
                  kubelet = list(object(
                    {
                      cluster_dns_server           = string
                      cluster_domain               = string
                      extra_args                   = map(string)
                      extra_binds                  = list(string)
                      extra_env                    = list(string)
                      fail_swap_on                 = bool
                      generate_serving_certificate = bool
                      image                        = string
                      infra_container_image        = string
                    }
                  ))
                  kubeproxy = list(object(
                    {
                      extra_args  = map(string)
                      extra_binds = list(string)
                      extra_env   = list(string)
                      image       = string
                    }
                  ))
                  scheduler = list(object(
                    {
                      extra_args  = map(string)
                      extra_binds = list(string)
                      extra_env   = list(string)
                      image       = string
                    }
                  ))
                }
              ))
              ssh_agent_auth = bool
              ssh_cert_path  = string
              ssh_key_path   = string
              upgrade_strategy = list(object(
                {
                  drain = bool
                  drain_input = list(object(
                    {
                      delete_local_data  = bool
                      force              = bool
                      grace_period       = number
                      ignore_daemon_sets = bool
                      timeout            = number
                    }
                  ))
                  max_unavailable_controlplane = string
                  max_unavailable_worker       = string
                }
              ))
              win_prefix_path = string
            }
          ))
          scheduled_cluster_scan = list(object(
            {
              enabled = bool
              scan_config = list(object(
                {
                  cis_scan_config = list(object(
                    {
                      debug_master               = bool
                      debug_worker               = bool
                      override_benchmark_version = string
                      override_skip              = list(string)
                      profile                    = string
                    }
                  ))
                }
              ))
              schedule_config = list(object(
                {
                  cron_schedule = string
                  retention     = number
                }
              ))
            }
          ))
          windows_prefered_cluster = bool
        }
      ))
      cluster_template_id = string
      default             = bool
      enabled             = bool
      id                  = string
      labels              = map(string)
      name                = string
      questions = list(object(
        {
          default  = string
          required = bool
          type     = string
          variable = string
        }
      ))
    }
  ))
  default = []
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
resource "rancher2_cluster_template" "this" {
  annotations = var.annotations
  description = var.description
  labels      = var.labels
  name        = var.name

  dynamic "members" {
    for_each = var.members
    content {
      access_type        = members.value["access_type"]
      group_principal_id = members.value["group_principal_id"]
      user_principal_id  = members.value["user_principal_id"]
    }
  }

  dynamic "template_revisions" {
    for_each = var.template_revisions
    content {
      annotations = template_revisions.value["annotations"]
      default     = template_revisions.value["default"]
      enabled     = template_revisions.value["enabled"]
      labels      = template_revisions.value["labels"]
      name        = template_revisions.value["name"]

      dynamic "cluster_config" {
        for_each = template_revisions.value.cluster_config
        content {
          default_cluster_role_for_project_members = cluster_config.value["default_cluster_role_for_project_members"]
          default_pod_security_policy_template_id  = cluster_config.value["default_pod_security_policy_template_id"]
          desired_agent_image                      = cluster_config.value["desired_agent_image"]
          desired_auth_image                       = cluster_config.value["desired_auth_image"]
          docker_root_dir                          = cluster_config.value["docker_root_dir"]
          enable_cluster_alerting                  = cluster_config.value["enable_cluster_alerting"]
          enable_cluster_monitoring                = cluster_config.value["enable_cluster_monitoring"]
          enable_network_policy                    = cluster_config.value["enable_network_policy"]
          windows_prefered_cluster                 = cluster_config.value["windows_prefered_cluster"]

          dynamic "cluster_auth_endpoint" {
            for_each = cluster_config.value.cluster_auth_endpoint
            content {
              ca_certs = cluster_auth_endpoint.value["ca_certs"]
              enabled  = cluster_auth_endpoint.value["enabled"]
              fqdn     = cluster_auth_endpoint.value["fqdn"]
            }
          }

          dynamic "rke_config" {
            for_each = cluster_config.value.rke_config
            content {
              addon_job_timeout     = rke_config.value["addon_job_timeout"]
              addons                = rke_config.value["addons"]
              addons_include        = rke_config.value["addons_include"]
              ignore_docker_version = rke_config.value["ignore_docker_version"]
              kubernetes_version    = rke_config.value["kubernetes_version"]
              prefix_path           = rke_config.value["prefix_path"]
              ssh_agent_auth        = rke_config.value["ssh_agent_auth"]
              ssh_cert_path         = rke_config.value["ssh_cert_path"]
              ssh_key_path          = rke_config.value["ssh_key_path"]
              win_prefix_path       = rke_config.value["win_prefix_path"]

              dynamic "authentication" {
                for_each = rke_config.value.authentication
                content {
                  sans     = authentication.value["sans"]
                  strategy = authentication.value["strategy"]
                }
              }

              dynamic "authorization" {
                for_each = rke_config.value.authorization
                content {
                  mode    = authorization.value["mode"]
                  options = authorization.value["options"]
                }
              }

              dynamic "bastion_host" {
                for_each = rke_config.value.bastion_host
                content {
                  address        = bastion_host.value["address"]
                  port           = bastion_host.value["port"]
                  ssh_agent_auth = bastion_host.value["ssh_agent_auth"]
                  ssh_key        = bastion_host.value["ssh_key"]
                  ssh_key_path   = bastion_host.value["ssh_key_path"]
                  user           = bastion_host.value["user"]
                }
              }

              dynamic "cloud_provider" {
                for_each = rke_config.value.cloud_provider
                content {
                  custom_cloud_provider = cloud_provider.value["custom_cloud_provider"]
                  name                  = cloud_provider.value["name"]

                  dynamic "aws_cloud_provider" {
                    for_each = cloud_provider.value.aws_cloud_provider
                    content {

                      dynamic "global" {
                        for_each = aws_cloud_provider.value.global
                        content {
                          disable_security_group_ingress = global.value["disable_security_group_ingress"]
                          disable_strict_zone_check      = global.value["disable_strict_zone_check"]
                          elb_security_group             = global.value["elb_security_group"]
                          kubernetes_cluster_id          = global.value["kubernetes_cluster_id"]
                          kubernetes_cluster_tag         = global.value["kubernetes_cluster_tag"]
                          role_arn                       = global.value["role_arn"]
                          route_table_id                 = global.value["route_table_id"]
                          subnet_id                      = global.value["subnet_id"]
                          vpc                            = global.value["vpc"]
                          zone                           = global.value["zone"]
                        }
                      }

                      dynamic "service_override" {
                        for_each = aws_cloud_provider.value.service_override
                        content {
                          region         = service_override.value["region"]
                          service        = service_override.value["service"]
                          signing_method = service_override.value["signing_method"]
                          signing_name   = service_override.value["signing_name"]
                          signing_region = service_override.value["signing_region"]
                          url            = service_override.value["url"]
                        }
                      }

                    }
                  }

                  dynamic "azure_cloud_provider" {
                    for_each = cloud_provider.value.azure_cloud_provider
                    content {
                      aad_client_cert_password         = azure_cloud_provider.value["aad_client_cert_password"]
                      aad_client_cert_path             = azure_cloud_provider.value["aad_client_cert_path"]
                      aad_client_id                    = azure_cloud_provider.value["aad_client_id"]
                      aad_client_secret                = azure_cloud_provider.value["aad_client_secret"]
                      cloud                            = azure_cloud_provider.value["cloud"]
                      cloud_provider_backoff           = azure_cloud_provider.value["cloud_provider_backoff"]
                      cloud_provider_backoff_duration  = azure_cloud_provider.value["cloud_provider_backoff_duration"]
                      cloud_provider_backoff_exponent  = azure_cloud_provider.value["cloud_provider_backoff_exponent"]
                      cloud_provider_backoff_jitter    = azure_cloud_provider.value["cloud_provider_backoff_jitter"]
                      cloud_provider_backoff_retries   = azure_cloud_provider.value["cloud_provider_backoff_retries"]
                      cloud_provider_rate_limit        = azure_cloud_provider.value["cloud_provider_rate_limit"]
                      cloud_provider_rate_limit_bucket = azure_cloud_provider.value["cloud_provider_rate_limit_bucket"]
                      cloud_provider_rate_limit_qps    = azure_cloud_provider.value["cloud_provider_rate_limit_qps"]
                      load_balancer_sku                = azure_cloud_provider.value["load_balancer_sku"]
                      location                         = azure_cloud_provider.value["location"]
                      maximum_load_balancer_rule_count = azure_cloud_provider.value["maximum_load_balancer_rule_count"]
                      primary_availability_set_name    = azure_cloud_provider.value["primary_availability_set_name"]
                      primary_scale_set_name           = azure_cloud_provider.value["primary_scale_set_name"]
                      resource_group                   = azure_cloud_provider.value["resource_group"]
                      route_table_name                 = azure_cloud_provider.value["route_table_name"]
                      security_group_name              = azure_cloud_provider.value["security_group_name"]
                      subnet_name                      = azure_cloud_provider.value["subnet_name"]
                      subscription_id                  = azure_cloud_provider.value["subscription_id"]
                      tenant_id                        = azure_cloud_provider.value["tenant_id"]
                      use_instance_metadata            = azure_cloud_provider.value["use_instance_metadata"]
                      use_managed_identity_extension   = azure_cloud_provider.value["use_managed_identity_extension"]
                      vm_type                          = azure_cloud_provider.value["vm_type"]
                      vnet_name                        = azure_cloud_provider.value["vnet_name"]
                      vnet_resource_group              = azure_cloud_provider.value["vnet_resource_group"]
                    }
                  }

                  dynamic "openstack_cloud_provider" {
                    for_each = cloud_provider.value.openstack_cloud_provider
                    content {

                      dynamic "block_storage" {
                        for_each = openstack_cloud_provider.value.block_storage
                        content {
                          bs_version        = block_storage.value["bs_version"]
                          ignore_volume_az  = block_storage.value["ignore_volume_az"]
                          trust_device_path = block_storage.value["trust_device_path"]
                        }
                      }

                      dynamic "global" {
                        for_each = openstack_cloud_provider.value.global
                        content {
                          auth_url    = global.value["auth_url"]
                          ca_file     = global.value["ca_file"]
                          domain_id   = global.value["domain_id"]
                          domain_name = global.value["domain_name"]
                          password    = global.value["password"]
                          region      = global.value["region"]
                          tenant_id   = global.value["tenant_id"]
                          tenant_name = global.value["tenant_name"]
                          trust_id    = global.value["trust_id"]
                          username    = global.value["username"]
                        }
                      }

                      dynamic "load_balancer" {
                        for_each = openstack_cloud_provider.value.load_balancer
                        content {
                          create_monitor         = load_balancer.value["create_monitor"]
                          floating_network_id    = load_balancer.value["floating_network_id"]
                          lb_method              = load_balancer.value["lb_method"]
                          lb_provider            = load_balancer.value["lb_provider"]
                          lb_version             = load_balancer.value["lb_version"]
                          manage_security_groups = load_balancer.value["manage_security_groups"]
                          monitor_delay          = load_balancer.value["monitor_delay"]
                          monitor_max_retries    = load_balancer.value["monitor_max_retries"]
                          monitor_timeout        = load_balancer.value["monitor_timeout"]
                          subnet_id              = load_balancer.value["subnet_id"]
                          use_octavia            = load_balancer.value["use_octavia"]
                        }
                      }

                      dynamic "metadata" {
                        for_each = openstack_cloud_provider.value.metadata
                        content {
                          request_timeout = metadata.value["request_timeout"]
                          search_order    = metadata.value["search_order"]
                        }
                      }

                      dynamic "route" {
                        for_each = openstack_cloud_provider.value.route
                        content {
                          router_id = route.value["router_id"]
                        }
                      }

                    }
                  }

                  dynamic "vsphere_cloud_provider" {
                    for_each = cloud_provider.value.vsphere_cloud_provider
                    content {

                      dynamic "disk" {
                        for_each = vsphere_cloud_provider.value.disk
                        content {
                          scsi_controller_type = disk.value["scsi_controller_type"]
                        }
                      }

                      dynamic "global" {
                        for_each = vsphere_cloud_provider.value.global
                        content {
                          datacenters          = global.value["datacenters"]
                          insecure_flag        = global.value["insecure_flag"]
                          password             = global.value["password"]
                          port                 = global.value["port"]
                          soap_roundtrip_count = global.value["soap_roundtrip_count"]
                          user                 = global.value["user"]
                        }
                      }

                      dynamic "network" {
                        for_each = vsphere_cloud_provider.value.network
                        content {
                          public_network = network.value["public_network"]
                        }
                      }

                      dynamic "virtual_center" {
                        for_each = vsphere_cloud_provider.value.virtual_center
                        content {
                          datacenters          = virtual_center.value["datacenters"]
                          name                 = virtual_center.value["name"]
                          password             = virtual_center.value["password"]
                          port                 = virtual_center.value["port"]
                          soap_roundtrip_count = virtual_center.value["soap_roundtrip_count"]
                          user                 = virtual_center.value["user"]
                        }
                      }

                      dynamic "workspace" {
                        for_each = vsphere_cloud_provider.value.workspace
                        content {
                          datacenter        = workspace.value["datacenter"]
                          default_datastore = workspace.value["default_datastore"]
                          folder            = workspace.value["folder"]
                          resourcepool_path = workspace.value["resourcepool_path"]
                          server            = workspace.value["server"]
                        }
                      }

                    }
                  }

                }
              }

              dynamic "dns" {
                for_each = rke_config.value.dns
                content {
                  node_selector        = dns.value["node_selector"]
                  provider             = dns.value["provider"]
                  reverse_cidrs        = dns.value["reverse_cidrs"]
                  upstream_nameservers = dns.value["upstream_nameservers"]

                  dynamic "linear_autoscaler_params" {
                    for_each = dns.value.linear_autoscaler_params
                    content {
                      cores_per_replica            = linear_autoscaler_params.value["cores_per_replica"]
                      max                          = linear_autoscaler_params.value["max"]
                      min                          = linear_autoscaler_params.value["min"]
                      nodes_per_replica            = linear_autoscaler_params.value["nodes_per_replica"]
                      prevent_single_point_failure = linear_autoscaler_params.value["prevent_single_point_failure"]
                    }
                  }

                  dynamic "nodelocal" {
                    for_each = dns.value.nodelocal
                    content {
                      ip_address    = nodelocal.value["ip_address"]
                      node_selector = nodelocal.value["node_selector"]
                    }
                  }

                  dynamic "update_strategy" {
                    for_each = dns.value.update_strategy
                    content {
                      strategy = update_strategy.value["strategy"]

                      dynamic "rolling_update" {
                        for_each = update_strategy.value.rolling_update
                        content {
                          max_surge       = rolling_update.value["max_surge"]
                          max_unavailable = rolling_update.value["max_unavailable"]
                        }
                      }

                    }
                  }

                }
              }

              dynamic "ingress" {
                for_each = rke_config.value.ingress
                content {
                  dns_policy    = ingress.value["dns_policy"]
                  extra_args    = ingress.value["extra_args"]
                  node_selector = ingress.value["node_selector"]
                  options       = ingress.value["options"]
                  provider      = ingress.value["provider"]
                }
              }

              dynamic "monitoring" {
                for_each = rke_config.value.monitoring
                content {
                  node_selector = monitoring.value["node_selector"]
                  options       = monitoring.value["options"]
                  provider      = monitoring.value["provider"]
                  replicas      = monitoring.value["replicas"]

                  dynamic "update_strategy" {
                    for_each = monitoring.value.update_strategy
                    content {
                      strategy = update_strategy.value["strategy"]

                      dynamic "rolling_update" {
                        for_each = update_strategy.value.rolling_update
                        content {
                          max_surge       = rolling_update.value["max_surge"]
                          max_unavailable = rolling_update.value["max_unavailable"]
                        }
                      }

                    }
                  }

                }
              }

              dynamic "network" {
                for_each = rke_config.value.network
                content {
                  mtu     = network.value["mtu"]
                  options = network.value["options"]
                  plugin  = network.value["plugin"]

                  dynamic "calico_network_provider" {
                    for_each = network.value.calico_network_provider
                    content {
                      cloud_provider = calico_network_provider.value["cloud_provider"]
                    }
                  }

                  dynamic "canal_network_provider" {
                    for_each = network.value.canal_network_provider
                    content {
                      iface = canal_network_provider.value["iface"]
                    }
                  }

                  dynamic "flannel_network_provider" {
                    for_each = network.value.flannel_network_provider
                    content {
                      iface = flannel_network_provider.value["iface"]
                    }
                  }

                  dynamic "weave_network_provider" {
                    for_each = network.value.weave_network_provider
                    content {
                      password = weave_network_provider.value["password"]
                    }
                  }

                }
              }

              dynamic "nodes" {
                for_each = rke_config.value.nodes
                content {
                  address           = nodes.value["address"]
                  docker_socket     = nodes.value["docker_socket"]
                  hostname_override = nodes.value["hostname_override"]
                  internal_address  = nodes.value["internal_address"]
                  labels            = nodes.value["labels"]
                  node_id           = nodes.value["node_id"]
                  port              = nodes.value["port"]
                  role              = nodes.value["role"]
                  ssh_agent_auth    = nodes.value["ssh_agent_auth"]
                  ssh_key           = nodes.value["ssh_key"]
                  ssh_key_path      = nodes.value["ssh_key_path"]
                  user              = nodes.value["user"]
                }
              }

              dynamic "private_registries" {
                for_each = rke_config.value.private_registries
                content {
                  is_default = private_registries.value["is_default"]
                  password   = private_registries.value["password"]
                  url        = private_registries.value["url"]
                  user       = private_registries.value["user"]
                }
              }

              dynamic "services" {
                for_each = rke_config.value.services
                content {

                  dynamic "etcd" {
                    for_each = services.value.etcd
                    content {
                      ca_cert       = etcd.value["ca_cert"]
                      cert          = etcd.value["cert"]
                      creation      = etcd.value["creation"]
                      external_urls = etcd.value["external_urls"]
                      extra_args    = etcd.value["extra_args"]
                      extra_binds   = etcd.value["extra_binds"]
                      extra_env     = etcd.value["extra_env"]
                      gid           = etcd.value["gid"]
                      image         = etcd.value["image"]
                      key           = etcd.value["key"]
                      path          = etcd.value["path"]
                      retention     = etcd.value["retention"]
                      snapshot      = etcd.value["snapshot"]
                      uid           = etcd.value["uid"]

                      dynamic "backup_config" {
                        for_each = etcd.value.backup_config
                        content {
                          enabled        = backup_config.value["enabled"]
                          interval_hours = backup_config.value["interval_hours"]
                          retention      = backup_config.value["retention"]
                          safe_timestamp = backup_config.value["safe_timestamp"]
                          timeout        = backup_config.value["timeout"]

                          dynamic "s3_backup_config" {
                            for_each = backup_config.value.s3_backup_config
                            content {
                              access_key  = s3_backup_config.value["access_key"]
                              bucket_name = s3_backup_config.value["bucket_name"]
                              custom_ca   = s3_backup_config.value["custom_ca"]
                              endpoint    = s3_backup_config.value["endpoint"]
                              folder      = s3_backup_config.value["folder"]
                              region      = s3_backup_config.value["region"]
                              secret_key  = s3_backup_config.value["secret_key"]
                            }
                          }

                        }
                      }

                    }
                  }

                  dynamic "kube_api" {
                    for_each = services.value.kube_api
                    content {
                      admission_configuration  = kube_api.value["admission_configuration"]
                      always_pull_images       = kube_api.value["always_pull_images"]
                      extra_args               = kube_api.value["extra_args"]
                      extra_binds              = kube_api.value["extra_binds"]
                      extra_env                = kube_api.value["extra_env"]
                      image                    = kube_api.value["image"]
                      pod_security_policy      = kube_api.value["pod_security_policy"]
                      service_cluster_ip_range = kube_api.value["service_cluster_ip_range"]
                      service_node_port_range  = kube_api.value["service_node_port_range"]

                      dynamic "audit_log" {
                        for_each = kube_api.value.audit_log
                        content {
                          enabled = audit_log.value["enabled"]

                          dynamic "configuration" {
                            for_each = audit_log.value.configuration
                            content {
                              format     = configuration.value["format"]
                              max_age    = configuration.value["max_age"]
                              max_backup = configuration.value["max_backup"]
                              max_size   = configuration.value["max_size"]
                              path       = configuration.value["path"]
                              policy     = configuration.value["policy"]
                            }
                          }

                        }
                      }

                      dynamic "event_rate_limit" {
                        for_each = kube_api.value.event_rate_limit
                        content {
                          configuration = event_rate_limit.value["configuration"]
                          enabled       = event_rate_limit.value["enabled"]
                        }
                      }

                      dynamic "secrets_encryption_config" {
                        for_each = kube_api.value.secrets_encryption_config
                        content {
                          custom_config = secrets_encryption_config.value["custom_config"]
                          enabled       = secrets_encryption_config.value["enabled"]
                        }
                      }

                    }
                  }

                  dynamic "kube_controller" {
                    for_each = services.value.kube_controller
                    content {
                      cluster_cidr             = kube_controller.value["cluster_cidr"]
                      extra_args               = kube_controller.value["extra_args"]
                      extra_binds              = kube_controller.value["extra_binds"]
                      extra_env                = kube_controller.value["extra_env"]
                      image                    = kube_controller.value["image"]
                      service_cluster_ip_range = kube_controller.value["service_cluster_ip_range"]
                    }
                  }

                  dynamic "kubelet" {
                    for_each = services.value.kubelet
                    content {
                      cluster_dns_server           = kubelet.value["cluster_dns_server"]
                      cluster_domain               = kubelet.value["cluster_domain"]
                      extra_args                   = kubelet.value["extra_args"]
                      extra_binds                  = kubelet.value["extra_binds"]
                      extra_env                    = kubelet.value["extra_env"]
                      fail_swap_on                 = kubelet.value["fail_swap_on"]
                      generate_serving_certificate = kubelet.value["generate_serving_certificate"]
                      image                        = kubelet.value["image"]
                      infra_container_image        = kubelet.value["infra_container_image"]
                    }
                  }

                  dynamic "kubeproxy" {
                    for_each = services.value.kubeproxy
                    content {
                      extra_args  = kubeproxy.value["extra_args"]
                      extra_binds = kubeproxy.value["extra_binds"]
                      extra_env   = kubeproxy.value["extra_env"]
                      image       = kubeproxy.value["image"]
                    }
                  }

                  dynamic "scheduler" {
                    for_each = services.value.scheduler
                    content {
                      extra_args  = scheduler.value["extra_args"]
                      extra_binds = scheduler.value["extra_binds"]
                      extra_env   = scheduler.value["extra_env"]
                      image       = scheduler.value["image"]
                    }
                  }

                }
              }

              dynamic "upgrade_strategy" {
                for_each = rke_config.value.upgrade_strategy
                content {
                  drain                        = upgrade_strategy.value["drain"]
                  max_unavailable_controlplane = upgrade_strategy.value["max_unavailable_controlplane"]
                  max_unavailable_worker       = upgrade_strategy.value["max_unavailable_worker"]

                  dynamic "drain_input" {
                    for_each = upgrade_strategy.value.drain_input
                    content {
                      delete_local_data  = drain_input.value["delete_local_data"]
                      force              = drain_input.value["force"]
                      grace_period       = drain_input.value["grace_period"]
                      ignore_daemon_sets = drain_input.value["ignore_daemon_sets"]
                      timeout            = drain_input.value["timeout"]
                    }
                  }

                }
              }

            }
          }

          dynamic "scheduled_cluster_scan" {
            for_each = cluster_config.value.scheduled_cluster_scan
            content {
              enabled = scheduled_cluster_scan.value["enabled"]

              dynamic "scan_config" {
                for_each = scheduled_cluster_scan.value.scan_config
                content {

                  dynamic "cis_scan_config" {
                    for_each = scan_config.value.cis_scan_config
                    content {
                      debug_master               = cis_scan_config.value["debug_master"]
                      debug_worker               = cis_scan_config.value["debug_worker"]
                      override_benchmark_version = cis_scan_config.value["override_benchmark_version"]
                      override_skip              = cis_scan_config.value["override_skip"]
                      profile                    = cis_scan_config.value["profile"]
                    }
                  }

                }
              }

              dynamic "schedule_config" {
                for_each = scheduled_cluster_scan.value.schedule_config
                content {
                  cron_schedule = schedule_config.value["cron_schedule"]
                  retention     = schedule_config.value["retention"]
                }
              }

            }
          }

        }
      }

      dynamic "questions" {
        for_each = template_revisions.value.questions
        content {
          default  = questions.value["default"]
          required = questions.value["required"]
          type     = questions.value["type"]
          variable = questions.value["variable"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = rancher2_cluster_template.this.annotations
}

output "default_revision_id" {
  description = "returns a string"
  value       = rancher2_cluster_template.this.default_revision_id
}

output "id" {
  description = "returns a string"
  value       = rancher2_cluster_template.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_cluster_template.this.labels
}

output "this" {
  value = rancher2_cluster_template.this
}
```

[top](#index)