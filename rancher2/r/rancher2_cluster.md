# rancher2_cluster

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
module "rancher2_cluster" {
  source = "./modules/rancher2/r/rancher2_cluster"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # cluster_template_id - (optional) is a type of string
  cluster_template_id = null
  # cluster_template_revision_id - (optional) is a type of string
  cluster_template_revision_id = null
  # default_pod_security_policy_template_id - (optional) is a type of string
  default_pod_security_policy_template_id = null
  # description - (optional) is a type of string
  description = null
  # desired_agent_image - (optional) is a type of string
  desired_agent_image = null
  # desired_auth_image - (optional) is a type of string
  desired_auth_image = null
  # docker_root_dir - (optional) is a type of string
  docker_root_dir = null
  # driver - (optional) is a type of string
  driver = null
  # enable_cluster_alerting - (optional) is a type of bool
  enable_cluster_alerting = null
  # enable_cluster_monitoring - (optional) is a type of bool
  enable_cluster_monitoring = null
  # enable_network_policy - (optional) is a type of bool
  enable_network_policy = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # windows_prefered_cluster - (optional) is a type of bool
  windows_prefered_cluster = null

  aks_config = [{
    aad_server_app_secret                  = null
    aad_tenant_id                          = null
    add_client_app_id                      = null
    add_server_app_id                      = null
    admin_username                         = null
    agent_dns_prefix                       = null
    agent_os_disk_size                     = null
    agent_pool_name                        = null
    agent_storage_profile                  = null
    agent_vm_size                          = null
    auth_base_url                          = null
    base_url                               = null
    client_id                              = null
    client_secret                          = null
    count                                  = null
    dns_service_ip                         = null
    docker_bridge_cidr                     = null
    enable_http_application_routing        = null
    enable_monitoring                      = null
    kubernetes_version                     = null
    load_balancer_sku                      = null
    location                               = null
    log_analytics_workspace                = null
    log_analytics_workspace_resource_group = null
    master_dns_prefix                      = null
    max_pods                               = null
    network_plugin                         = null
    network_policy                         = null
    pod_cidr                               = null
    resource_group                         = null
    service_cidr                           = null
    ssh_public_key_contents                = null
    subnet                                 = null
    subscription_id                        = null
    tag                                    = {}
    tenant_id                              = null
    virtual_network                        = null
    virtual_network_resource_group         = null
  }]

  cluster_auth_endpoint = [{
    ca_certs = null
    enabled  = null
    fqdn     = null
  }]

  cluster_monitoring_input = [{
    answers = {}
    version = null
  }]

  cluster_template_answers = [{
    cluster_id = null
    project_id = null
    values     = {}
  }]

  cluster_template_questions = [{
    default  = null
    required = null
    type     = null
    variable = null
  }]

  eks_config = [{
    access_key                      = null
    ami                             = null
    associate_worker_node_public_ip = null
    desired_nodes                   = null
    ebs_encryption                  = null
    instance_type                   = null
    key_pair_name                   = null
    kubernetes_version              = null
    maximum_nodes                   = null
    minimum_nodes                   = null
    node_volume_size                = null
    region                          = null
    secret_key                      = null
    security_groups                 = []
    service_role                    = null
    session_token                   = null
    subnets                         = []
    user_data                       = null
    virtual_network                 = null
  }]

  eks_config_v2 = [{
    cloud_credential_id = null
    imported            = null
    kms_key             = null
    kubernetes_version  = null
    logging_types       = []
    name                = null
    node_groups = [{
      desired_size  = null
      disk_size     = null
      ec2_ssh_key   = null
      gpu           = null
      image_id      = null
      instance_type = null
      labels        = {}
      launch_template = [{
        id      = null
        name    = null
        version = null
      }]
      max_size               = null
      min_size               = null
      name                   = null
      request_spot_instances = null
      resource_tags          = {}
      spot_instance_types    = []
      subnets                = []
      tags                   = {}
      user_data              = null
      version                = null
    }]
    private_access        = null
    public_access         = null
    public_access_sources = []
    region                = null
    secrets_encryption    = null
    security_groups       = []
    service_role          = null
    subnets               = []
    tags                  = {}
  }]

  gke_config = [{
    cluster_ipv4_cidr                       = null
    credential                              = null
    description                             = null
    disk_size_gb                            = null
    disk_type                               = null
    enable_alpha_feature                    = null
    enable_auto_repair                      = null
    enable_auto_upgrade                     = null
    enable_horizontal_pod_autoscaling       = null
    enable_http_load_balancing              = null
    enable_kubernetes_dashboard             = null
    enable_legacy_abac                      = null
    enable_master_authorized_network        = null
    enable_network_policy_config            = null
    enable_nodepool_autoscaling             = null
    enable_private_endpoint                 = null
    enable_private_nodes                    = null
    enable_stackdriver_logging              = null
    enable_stackdriver_monitoring           = null
    image_type                              = null
    ip_policy_cluster_ipv4_cidr_block       = null
    ip_policy_cluster_secondary_range_name  = null
    ip_policy_create_subnetwork             = null
    ip_policy_node_ipv4_cidr_block          = null
    ip_policy_services_ipv4_cidr_block      = null
    ip_policy_services_secondary_range_name = null
    ip_policy_subnetwork_name               = null
    issue_client_certificate                = null
    kubernetes_dashboard                    = null
    labels                                  = {}
    local_ssd_count                         = null
    locations                               = []
    machine_type                            = null
    maintenance_window                      = null
    master_authorized_network_cidr_blocks   = []
    master_ipv4_cidr_block                  = null
    master_version                          = null
    max_node_count                          = null
    min_node_count                          = null
    network                                 = null
    node_count                              = null
    node_pool                               = null
    node_version                            = null
    oauth_scopes                            = []
    preemptible                             = null
    project_id                              = null
    region                                  = null
    resource_labels                         = {}
    service_account                         = null
    sub_network                             = null
    taints                                  = []
    use_ip_aliases                          = null
    zone                                    = null
  }]

  k3s_config = [{
    upgrade_strategy = [{
      drain_server_nodes = null
      drain_worker_nodes = null
      server_concurrency = null
      worker_concurrency = null
    }]
    version = null
  }]

  oke_config = [{
    compartment_id              = null
    custom_boot_volume_size     = null
    description                 = null
    enable_kubernetes_dashboard = null
    enable_private_nodes        = null
    fingerprint                 = null
    flex_ocpus                  = null
    kubernetes_version          = null
    load_balancer_subnet_name_1 = null
    load_balancer_subnet_name_2 = null
    node_image                  = null
    node_pool_dns_domain_name   = null
    node_pool_subnet_name       = null
    node_public_key_contents    = null
    node_shape                  = null
    private_key_contents        = null
    private_key_passphrase      = null
    quantity_of_node_subnets    = null
    quantity_per_subnet         = null
    region                      = null
    service_dns_domain_name     = null
    skip_vcn_delete             = null
    tenancy_id                  = null
    user_ocid                   = null
    vcn_compartment_id          = null
    vcn_name                    = null
    worker_node_ingress_cidr    = null
  }]

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

variable "cluster_template_id" {
  description = "(optional) - Cluster template ID"
  type        = string
  default     = null
}

variable "cluster_template_revision_id" {
  description = "(optional) - Cluster template revision ID"
  type        = string
  default     = null
}

variable "default_pod_security_policy_template_id" {
  description = "(optional) - Default pod security policy template id"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "desired_agent_image" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "desired_auth_image" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "docker_root_dir" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "driver" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_cluster_alerting" {
  description = "(optional) - Enable built-in cluster alerting"
  type        = bool
  default     = null
}

variable "enable_cluster_monitoring" {
  description = "(optional) - Enable built-in cluster monitoring"
  type        = bool
  default     = null
}

variable "enable_network_policy" {
  description = "(optional) - Enable project network isolation"
  type        = bool
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "windows_prefered_cluster" {
  description = "(optional) - Windows preferred cluster"
  type        = bool
  default     = null
}

variable "aks_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      aad_server_app_secret                  = string
      aad_tenant_id                          = string
      add_client_app_id                      = string
      add_server_app_id                      = string
      admin_username                         = string
      agent_dns_prefix                       = string
      agent_os_disk_size                     = number
      agent_pool_name                        = string
      agent_storage_profile                  = string
      agent_vm_size                          = string
      auth_base_url                          = string
      base_url                               = string
      client_id                              = string
      client_secret                          = string
      count                                  = number
      dns_service_ip                         = string
      docker_bridge_cidr                     = string
      enable_http_application_routing        = bool
      enable_monitoring                      = bool
      kubernetes_version                     = string
      load_balancer_sku                      = string
      location                               = string
      log_analytics_workspace                = string
      log_analytics_workspace_resource_group = string
      master_dns_prefix                      = string
      max_pods                               = number
      network_plugin                         = string
      network_policy                         = string
      pod_cidr                               = string
      resource_group                         = string
      service_cidr                           = string
      ssh_public_key_contents                = string
      subnet                                 = string
      subscription_id                        = string
      tag                                    = map(string)
      tenant_id                              = string
      virtual_network                        = string
      virtual_network_resource_group         = string
    }
  ))
  default = []
}

variable "cluster_auth_endpoint" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ca_certs = string
      enabled  = bool
      fqdn     = string
    }
  ))
  default = []
}

variable "cluster_monitoring_input" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      answers = map(string)
      version = string
    }
  ))
  default = []
}

variable "cluster_template_answers" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cluster_id = string
      project_id = string
      values     = map(string)
    }
  ))
  default = []
}

variable "cluster_template_questions" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      default  = string
      required = bool
      type     = string
      variable = string
    }
  ))
  default = []
}

variable "eks_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      access_key                      = string
      ami                             = string
      associate_worker_node_public_ip = bool
      desired_nodes                   = number
      ebs_encryption                  = bool
      instance_type                   = string
      key_pair_name                   = string
      kubernetes_version              = string
      maximum_nodes                   = number
      minimum_nodes                   = number
      node_volume_size                = number
      region                          = string
      secret_key                      = string
      security_groups                 = list(string)
      service_role                    = string
      session_token                   = string
      subnets                         = list(string)
      user_data                       = string
      virtual_network                 = string
    }
  ))
  default = []
}

variable "eks_config_v2" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cloud_credential_id = string
      imported            = bool
      kms_key             = string
      kubernetes_version  = string
      logging_types       = list(string)
      name                = string
      node_groups = list(object(
        {
          desired_size  = number
          disk_size     = number
          ec2_ssh_key   = string
          gpu           = bool
          image_id      = string
          instance_type = string
          labels        = map(string)
          launch_template = list(object(
            {
              id      = string
              name    = string
              version = number
            }
          ))
          max_size               = number
          min_size               = number
          name                   = string
          request_spot_instances = bool
          resource_tags          = map(string)
          spot_instance_types    = list(string)
          subnets                = list(string)
          tags                   = map(string)
          user_data              = string
          version                = string
        }
      ))
      private_access        = bool
      public_access         = bool
      public_access_sources = list(string)
      region                = string
      secrets_encryption    = bool
      security_groups       = list(string)
      service_role          = string
      subnets               = list(string)
      tags                  = map(string)
    }
  ))
  default = []
}

variable "gke_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cluster_ipv4_cidr                       = string
      credential                              = string
      description                             = string
      disk_size_gb                            = number
      disk_type                               = string
      enable_alpha_feature                    = bool
      enable_auto_repair                      = bool
      enable_auto_upgrade                     = bool
      enable_horizontal_pod_autoscaling       = bool
      enable_http_load_balancing              = bool
      enable_kubernetes_dashboard             = bool
      enable_legacy_abac                      = bool
      enable_master_authorized_network        = bool
      enable_network_policy_config            = bool
      enable_nodepool_autoscaling             = bool
      enable_private_endpoint                 = bool
      enable_private_nodes                    = bool
      enable_stackdriver_logging              = bool
      enable_stackdriver_monitoring           = bool
      image_type                              = string
      ip_policy_cluster_ipv4_cidr_block       = string
      ip_policy_cluster_secondary_range_name  = string
      ip_policy_create_subnetwork             = bool
      ip_policy_node_ipv4_cidr_block          = string
      ip_policy_services_ipv4_cidr_block      = string
      ip_policy_services_secondary_range_name = string
      ip_policy_subnetwork_name               = string
      issue_client_certificate                = bool
      kubernetes_dashboard                    = bool
      labels                                  = map(string)
      local_ssd_count                         = number
      locations                               = list(string)
      machine_type                            = string
      maintenance_window                      = string
      master_authorized_network_cidr_blocks   = list(string)
      master_ipv4_cidr_block                  = string
      master_version                          = string
      max_node_count                          = number
      min_node_count                          = number
      network                                 = string
      node_count                              = number
      node_pool                               = string
      node_version                            = string
      oauth_scopes                            = list(string)
      preemptible                             = bool
      project_id                              = string
      region                                  = string
      resource_labels                         = map(string)
      service_account                         = string
      sub_network                             = string
      taints                                  = list(string)
      use_ip_aliases                          = bool
      zone                                    = string
    }
  ))
  default = []
}

variable "k3s_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      upgrade_strategy = list(object(
        {
          drain_server_nodes = bool
          drain_worker_nodes = bool
          server_concurrency = number
          worker_concurrency = number
        }
      ))
      version = string
    }
  ))
  default = []
}

variable "oke_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      compartment_id              = string
      custom_boot_volume_size     = number
      description                 = string
      enable_kubernetes_dashboard = bool
      enable_private_nodes        = bool
      fingerprint                 = string
      flex_ocpus                  = number
      kubernetes_version          = string
      load_balancer_subnet_name_1 = string
      load_balancer_subnet_name_2 = string
      node_image                  = string
      node_pool_dns_domain_name   = string
      node_pool_subnet_name       = string
      node_public_key_contents    = string
      node_shape                  = string
      private_key_contents        = string
      private_key_passphrase      = string
      quantity_of_node_subnets    = number
      quantity_per_subnet         = number
      region                      = string
      service_dns_domain_name     = string
      skip_vcn_delete             = bool
      tenancy_id                  = string
      user_ocid                   = string
      vcn_compartment_id          = string
      vcn_name                    = string
      worker_node_ingress_cidr    = string
    }
  ))
  default = []
}

variable "rke_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
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
  default = []
}

variable "scheduled_cluster_scan" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
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
resource "rancher2_cluster" "this" {
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # cluster_template_id - (optional) is a type of string
  cluster_template_id = var.cluster_template_id
  # cluster_template_revision_id - (optional) is a type of string
  cluster_template_revision_id = var.cluster_template_revision_id
  # default_pod_security_policy_template_id - (optional) is a type of string
  default_pod_security_policy_template_id = var.default_pod_security_policy_template_id
  # description - (optional) is a type of string
  description = var.description
  # desired_agent_image - (optional) is a type of string
  desired_agent_image = var.desired_agent_image
  # desired_auth_image - (optional) is a type of string
  desired_auth_image = var.desired_auth_image
  # docker_root_dir - (optional) is a type of string
  docker_root_dir = var.docker_root_dir
  # driver - (optional) is a type of string
  driver = var.driver
  # enable_cluster_alerting - (optional) is a type of bool
  enable_cluster_alerting = var.enable_cluster_alerting
  # enable_cluster_monitoring - (optional) is a type of bool
  enable_cluster_monitoring = var.enable_cluster_monitoring
  # enable_network_policy - (optional) is a type of bool
  enable_network_policy = var.enable_network_policy
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # windows_prefered_cluster - (optional) is a type of bool
  windows_prefered_cluster = var.windows_prefered_cluster

  dynamic "aks_config" {
    for_each = var.aks_config
    content {
      # aad_server_app_secret - (optional) is a type of string
      aad_server_app_secret = aks_config.value["aad_server_app_secret"]
      # aad_tenant_id - (optional) is a type of string
      aad_tenant_id = aks_config.value["aad_tenant_id"]
      # add_client_app_id - (optional) is a type of string
      add_client_app_id = aks_config.value["add_client_app_id"]
      # add_server_app_id - (optional) is a type of string
      add_server_app_id = aks_config.value["add_server_app_id"]
      # admin_username - (optional) is a type of string
      admin_username = aks_config.value["admin_username"]
      # agent_dns_prefix - (required) is a type of string
      agent_dns_prefix = aks_config.value["agent_dns_prefix"]
      # agent_os_disk_size - (optional) is a type of number
      agent_os_disk_size = aks_config.value["agent_os_disk_size"]
      # agent_pool_name - (optional) is a type of string
      agent_pool_name = aks_config.value["agent_pool_name"]
      # agent_storage_profile - (optional) is a type of string
      agent_storage_profile = aks_config.value["agent_storage_profile"]
      # agent_vm_size - (optional) is a type of string
      agent_vm_size = aks_config.value["agent_vm_size"]
      # auth_base_url - (optional) is a type of string
      auth_base_url = aks_config.value["auth_base_url"]
      # base_url - (optional) is a type of string
      base_url = aks_config.value["base_url"]
      # client_id - (required) is a type of string
      client_id = aks_config.value["client_id"]
      # client_secret - (required) is a type of string
      client_secret = aks_config.value["client_secret"]
      # count - (optional) is a type of number
      count = aks_config.value["count"]
      # dns_service_ip - (optional) is a type of string
      dns_service_ip = aks_config.value["dns_service_ip"]
      # docker_bridge_cidr - (optional) is a type of string
      docker_bridge_cidr = aks_config.value["docker_bridge_cidr"]
      # enable_http_application_routing - (optional) is a type of bool
      enable_http_application_routing = aks_config.value["enable_http_application_routing"]
      # enable_monitoring - (optional) is a type of bool
      enable_monitoring = aks_config.value["enable_monitoring"]
      # kubernetes_version - (required) is a type of string
      kubernetes_version = aks_config.value["kubernetes_version"]
      # load_balancer_sku - (optional) is a type of string
      load_balancer_sku = aks_config.value["load_balancer_sku"]
      # location - (optional) is a type of string
      location = aks_config.value["location"]
      # log_analytics_workspace - (optional) is a type of string
      log_analytics_workspace = aks_config.value["log_analytics_workspace"]
      # log_analytics_workspace_resource_group - (optional) is a type of string
      log_analytics_workspace_resource_group = aks_config.value["log_analytics_workspace_resource_group"]
      # master_dns_prefix - (required) is a type of string
      master_dns_prefix = aks_config.value["master_dns_prefix"]
      # max_pods - (optional) is a type of number
      max_pods = aks_config.value["max_pods"]
      # network_plugin - (optional) is a type of string
      network_plugin = aks_config.value["network_plugin"]
      # network_policy - (optional) is a type of string
      network_policy = aks_config.value["network_policy"]
      # pod_cidr - (optional) is a type of string
      pod_cidr = aks_config.value["pod_cidr"]
      # resource_group - (required) is a type of string
      resource_group = aks_config.value["resource_group"]
      # service_cidr - (optional) is a type of string
      service_cidr = aks_config.value["service_cidr"]
      # ssh_public_key_contents - (required) is a type of string
      ssh_public_key_contents = aks_config.value["ssh_public_key_contents"]
      # subnet - (required) is a type of string
      subnet = aks_config.value["subnet"]
      # subscription_id - (required) is a type of string
      subscription_id = aks_config.value["subscription_id"]
      # tag - (optional) is a type of map of string
      tag = aks_config.value["tag"]
      # tenant_id - (required) is a type of string
      tenant_id = aks_config.value["tenant_id"]
      # virtual_network - (required) is a type of string
      virtual_network = aks_config.value["virtual_network"]
      # virtual_network_resource_group - (required) is a type of string
      virtual_network_resource_group = aks_config.value["virtual_network_resource_group"]
    }
  }

  dynamic "cluster_auth_endpoint" {
    for_each = var.cluster_auth_endpoint
    content {
      # ca_certs - (optional) is a type of string
      ca_certs = cluster_auth_endpoint.value["ca_certs"]
      # enabled - (optional) is a type of bool
      enabled = cluster_auth_endpoint.value["enabled"]
      # fqdn - (optional) is a type of string
      fqdn = cluster_auth_endpoint.value["fqdn"]
    }
  }

  dynamic "cluster_monitoring_input" {
    for_each = var.cluster_monitoring_input
    content {
      # answers - (optional) is a type of map of string
      answers = cluster_monitoring_input.value["answers"]
      # version - (optional) is a type of string
      version = cluster_monitoring_input.value["version"]
    }
  }

  dynamic "cluster_template_answers" {
    for_each = var.cluster_template_answers
    content {
      # cluster_id - (optional) is a type of string
      cluster_id = cluster_template_answers.value["cluster_id"]
      # project_id - (optional) is a type of string
      project_id = cluster_template_answers.value["project_id"]
      # values - (optional) is a type of map of string
      values = cluster_template_answers.value["values"]
    }
  }

  dynamic "cluster_template_questions" {
    for_each = var.cluster_template_questions
    content {
      # default - (required) is a type of string
      default = cluster_template_questions.value["default"]
      # required - (optional) is a type of bool
      required = cluster_template_questions.value["required"]
      # type - (optional) is a type of string
      type = cluster_template_questions.value["type"]
      # variable - (required) is a type of string
      variable = cluster_template_questions.value["variable"]
    }
  }

  dynamic "eks_config" {
    for_each = var.eks_config
    content {
      # access_key - (required) is a type of string
      access_key = eks_config.value["access_key"]
      # ami - (optional) is a type of string
      ami = eks_config.value["ami"]
      # associate_worker_node_public_ip - (optional) is a type of bool
      associate_worker_node_public_ip = eks_config.value["associate_worker_node_public_ip"]
      # desired_nodes - (optional) is a type of number
      desired_nodes = eks_config.value["desired_nodes"]
      # ebs_encryption - (optional) is a type of bool
      ebs_encryption = eks_config.value["ebs_encryption"]
      # instance_type - (optional) is a type of string
      instance_type = eks_config.value["instance_type"]
      # key_pair_name - (optional) is a type of string
      key_pair_name = eks_config.value["key_pair_name"]
      # kubernetes_version - (required) is a type of string
      kubernetes_version = eks_config.value["kubernetes_version"]
      # maximum_nodes - (optional) is a type of number
      maximum_nodes = eks_config.value["maximum_nodes"]
      # minimum_nodes - (optional) is a type of number
      minimum_nodes = eks_config.value["minimum_nodes"]
      # node_volume_size - (optional) is a type of number
      node_volume_size = eks_config.value["node_volume_size"]
      # region - (optional) is a type of string
      region = eks_config.value["region"]
      # secret_key - (required) is a type of string
      secret_key = eks_config.value["secret_key"]
      # security_groups - (optional) is a type of list of string
      security_groups = eks_config.value["security_groups"]
      # service_role - (optional) is a type of string
      service_role = eks_config.value["service_role"]
      # session_token - (optional) is a type of string
      session_token = eks_config.value["session_token"]
      # subnets - (optional) is a type of list of string
      subnets = eks_config.value["subnets"]
      # user_data - (optional) is a type of string
      user_data = eks_config.value["user_data"]
      # virtual_network - (optional) is a type of string
      virtual_network = eks_config.value["virtual_network"]
    }
  }

  dynamic "eks_config_v2" {
    for_each = var.eks_config_v2
    content {
      # cloud_credential_id - (required) is a type of string
      cloud_credential_id = eks_config_v2.value["cloud_credential_id"]
      # imported - (optional) is a type of bool
      imported = eks_config_v2.value["imported"]
      # kms_key - (optional) is a type of string
      kms_key = eks_config_v2.value["kms_key"]
      # kubernetes_version - (optional) is a type of string
      kubernetes_version = eks_config_v2.value["kubernetes_version"]
      # logging_types - (optional) is a type of list of string
      logging_types = eks_config_v2.value["logging_types"]
      # name - (optional) is a type of string
      name = eks_config_v2.value["name"]
      # private_access - (optional) is a type of bool
      private_access = eks_config_v2.value["private_access"]
      # public_access - (optional) is a type of bool
      public_access = eks_config_v2.value["public_access"]
      # public_access_sources - (optional) is a type of list of string
      public_access_sources = eks_config_v2.value["public_access_sources"]
      # region - (optional) is a type of string
      region = eks_config_v2.value["region"]
      # secrets_encryption - (optional) is a type of bool
      secrets_encryption = eks_config_v2.value["secrets_encryption"]
      # security_groups - (optional) is a type of list of string
      security_groups = eks_config_v2.value["security_groups"]
      # service_role - (optional) is a type of string
      service_role = eks_config_v2.value["service_role"]
      # subnets - (optional) is a type of list of string
      subnets = eks_config_v2.value["subnets"]
      # tags - (optional) is a type of map of string
      tags = eks_config_v2.value["tags"]

      dynamic "node_groups" {
        for_each = eks_config_v2.value.node_groups
        content {
          # desired_size - (optional) is a type of number
          desired_size = node_groups.value["desired_size"]
          # disk_size - (optional) is a type of number
          disk_size = node_groups.value["disk_size"]
          # ec2_ssh_key - (optional) is a type of string
          ec2_ssh_key = node_groups.value["ec2_ssh_key"]
          # gpu - (optional) is a type of bool
          gpu = node_groups.value["gpu"]
          # image_id - (optional) is a type of string
          image_id = node_groups.value["image_id"]
          # instance_type - (optional) is a type of string
          instance_type = node_groups.value["instance_type"]
          # labels - (optional) is a type of map of string
          labels = node_groups.value["labels"]
          # max_size - (optional) is a type of number
          max_size = node_groups.value["max_size"]
          # min_size - (optional) is a type of number
          min_size = node_groups.value["min_size"]
          # name - (required) is a type of string
          name = node_groups.value["name"]
          # request_spot_instances - (optional) is a type of bool
          request_spot_instances = node_groups.value["request_spot_instances"]
          # resource_tags - (optional) is a type of map of string
          resource_tags = node_groups.value["resource_tags"]
          # spot_instance_types - (optional) is a type of list of string
          spot_instance_types = node_groups.value["spot_instance_types"]
          # subnets - (optional) is a type of list of string
          subnets = node_groups.value["subnets"]
          # tags - (optional) is a type of map of string
          tags = node_groups.value["tags"]
          # user_data - (optional) is a type of string
          user_data = node_groups.value["user_data"]

          dynamic "launch_template" {
            for_each = node_groups.value.launch_template
            content {
              # id - (required) is a type of string
              id = launch_template.value["id"]
              # name - (optional) is a type of string
              name = launch_template.value["name"]
              # version - (optional) is a type of number
              version = launch_template.value["version"]
            }
          }

        }
      }

    }
  }

  dynamic "gke_config" {
    for_each = var.gke_config
    content {
      # cluster_ipv4_cidr - (required) is a type of string
      cluster_ipv4_cidr = gke_config.value["cluster_ipv4_cidr"]
      # credential - (required) is a type of string
      credential = gke_config.value["credential"]
      # description - (optional) is a type of string
      description = gke_config.value["description"]
      # disk_size_gb - (optional) is a type of number
      disk_size_gb = gke_config.value["disk_size_gb"]
      # disk_type - (required) is a type of string
      disk_type = gke_config.value["disk_type"]
      # enable_alpha_feature - (optional) is a type of bool
      enable_alpha_feature = gke_config.value["enable_alpha_feature"]
      # enable_auto_repair - (optional) is a type of bool
      enable_auto_repair = gke_config.value["enable_auto_repair"]
      # enable_auto_upgrade - (optional) is a type of bool
      enable_auto_upgrade = gke_config.value["enable_auto_upgrade"]
      # enable_horizontal_pod_autoscaling - (optional) is a type of bool
      enable_horizontal_pod_autoscaling = gke_config.value["enable_horizontal_pod_autoscaling"]
      # enable_http_load_balancing - (optional) is a type of bool
      enable_http_load_balancing = gke_config.value["enable_http_load_balancing"]
      # enable_kubernetes_dashboard - (optional) is a type of bool
      enable_kubernetes_dashboard = gke_config.value["enable_kubernetes_dashboard"]
      # enable_legacy_abac - (optional) is a type of bool
      enable_legacy_abac = gke_config.value["enable_legacy_abac"]
      # enable_master_authorized_network - (optional) is a type of bool
      enable_master_authorized_network = gke_config.value["enable_master_authorized_network"]
      # enable_network_policy_config - (optional) is a type of bool
      enable_network_policy_config = gke_config.value["enable_network_policy_config"]
      # enable_nodepool_autoscaling - (optional) is a type of bool
      enable_nodepool_autoscaling = gke_config.value["enable_nodepool_autoscaling"]
      # enable_private_endpoint - (optional) is a type of bool
      enable_private_endpoint = gke_config.value["enable_private_endpoint"]
      # enable_private_nodes - (optional) is a type of bool
      enable_private_nodes = gke_config.value["enable_private_nodes"]
      # enable_stackdriver_logging - (optional) is a type of bool
      enable_stackdriver_logging = gke_config.value["enable_stackdriver_logging"]
      # enable_stackdriver_monitoring - (optional) is a type of bool
      enable_stackdriver_monitoring = gke_config.value["enable_stackdriver_monitoring"]
      # image_type - (required) is a type of string
      image_type = gke_config.value["image_type"]
      # ip_policy_cluster_ipv4_cidr_block - (required) is a type of string
      ip_policy_cluster_ipv4_cidr_block = gke_config.value["ip_policy_cluster_ipv4_cidr_block"]
      # ip_policy_cluster_secondary_range_name - (required) is a type of string
      ip_policy_cluster_secondary_range_name = gke_config.value["ip_policy_cluster_secondary_range_name"]
      # ip_policy_create_subnetwork - (optional) is a type of bool
      ip_policy_create_subnetwork = gke_config.value["ip_policy_create_subnetwork"]
      # ip_policy_node_ipv4_cidr_block - (required) is a type of string
      ip_policy_node_ipv4_cidr_block = gke_config.value["ip_policy_node_ipv4_cidr_block"]
      # ip_policy_services_ipv4_cidr_block - (required) is a type of string
      ip_policy_services_ipv4_cidr_block = gke_config.value["ip_policy_services_ipv4_cidr_block"]
      # ip_policy_services_secondary_range_name - (required) is a type of string
      ip_policy_services_secondary_range_name = gke_config.value["ip_policy_services_secondary_range_name"]
      # ip_policy_subnetwork_name - (required) is a type of string
      ip_policy_subnetwork_name = gke_config.value["ip_policy_subnetwork_name"]
      # issue_client_certificate - (optional) is a type of bool
      issue_client_certificate = gke_config.value["issue_client_certificate"]
      # kubernetes_dashboard - (optional) is a type of bool
      kubernetes_dashboard = gke_config.value["kubernetes_dashboard"]
      # labels - (optional) is a type of map of string
      labels = gke_config.value["labels"]
      # local_ssd_count - (optional) is a type of number
      local_ssd_count = gke_config.value["local_ssd_count"]
      # locations - (required) is a type of list of string
      locations = gke_config.value["locations"]
      # machine_type - (required) is a type of string
      machine_type = gke_config.value["machine_type"]
      # maintenance_window - (required) is a type of string
      maintenance_window = gke_config.value["maintenance_window"]
      # master_authorized_network_cidr_blocks - (optional) is a type of list of string
      master_authorized_network_cidr_blocks = gke_config.value["master_authorized_network_cidr_blocks"]
      # master_ipv4_cidr_block - (required) is a type of string
      master_ipv4_cidr_block = gke_config.value["master_ipv4_cidr_block"]
      # master_version - (required) is a type of string
      master_version = gke_config.value["master_version"]
      # max_node_count - (optional) is a type of number
      max_node_count = gke_config.value["max_node_count"]
      # min_node_count - (optional) is a type of number
      min_node_count = gke_config.value["min_node_count"]
      # network - (required) is a type of string
      network = gke_config.value["network"]
      # node_count - (optional) is a type of number
      node_count = gke_config.value["node_count"]
      # node_pool - (required) is a type of string
      node_pool = gke_config.value["node_pool"]
      # node_version - (required) is a type of string
      node_version = gke_config.value["node_version"]
      # oauth_scopes - (required) is a type of list of string
      oauth_scopes = gke_config.value["oauth_scopes"]
      # preemptible - (optional) is a type of bool
      preemptible = gke_config.value["preemptible"]
      # project_id - (required) is a type of string
      project_id = gke_config.value["project_id"]
      # region - (optional) is a type of string
      region = gke_config.value["region"]
      # resource_labels - (optional) is a type of map of string
      resource_labels = gke_config.value["resource_labels"]
      # service_account - (required) is a type of string
      service_account = gke_config.value["service_account"]
      # sub_network - (required) is a type of string
      sub_network = gke_config.value["sub_network"]
      # taints - (optional) is a type of list of string
      taints = gke_config.value["taints"]
      # use_ip_aliases - (optional) is a type of bool
      use_ip_aliases = gke_config.value["use_ip_aliases"]
      # zone - (optional) is a type of string
      zone = gke_config.value["zone"]
    }
  }

  dynamic "k3s_config" {
    for_each = var.k3s_config
    content {
      # version - (optional) is a type of string
      version = k3s_config.value["version"]

      dynamic "upgrade_strategy" {
        for_each = k3s_config.value.upgrade_strategy
        content {
          # drain_server_nodes - (optional) is a type of bool
          drain_server_nodes = upgrade_strategy.value["drain_server_nodes"]
          # drain_worker_nodes - (optional) is a type of bool
          drain_worker_nodes = upgrade_strategy.value["drain_worker_nodes"]
          # server_concurrency - (optional) is a type of number
          server_concurrency = upgrade_strategy.value["server_concurrency"]
          # worker_concurrency - (optional) is a type of number
          worker_concurrency = upgrade_strategy.value["worker_concurrency"]
        }
      }

    }
  }

  dynamic "oke_config" {
    for_each = var.oke_config
    content {
      # compartment_id - (required) is a type of string
      compartment_id = oke_config.value["compartment_id"]
      # custom_boot_volume_size - (optional) is a type of number
      custom_boot_volume_size = oke_config.value["custom_boot_volume_size"]
      # description - (optional) is a type of string
      description = oke_config.value["description"]
      # enable_kubernetes_dashboard - (optional) is a type of bool
      enable_kubernetes_dashboard = oke_config.value["enable_kubernetes_dashboard"]
      # enable_private_nodes - (optional) is a type of bool
      enable_private_nodes = oke_config.value["enable_private_nodes"]
      # fingerprint - (required) is a type of string
      fingerprint = oke_config.value["fingerprint"]
      # flex_ocpus - (optional) is a type of number
      flex_ocpus = oke_config.value["flex_ocpus"]
      # kubernetes_version - (required) is a type of string
      kubernetes_version = oke_config.value["kubernetes_version"]
      # load_balancer_subnet_name_1 - (optional) is a type of string
      load_balancer_subnet_name_1 = oke_config.value["load_balancer_subnet_name_1"]
      # load_balancer_subnet_name_2 - (optional) is a type of string
      load_balancer_subnet_name_2 = oke_config.value["load_balancer_subnet_name_2"]
      # node_image - (required) is a type of string
      node_image = oke_config.value["node_image"]
      # node_pool_dns_domain_name - (optional) is a type of string
      node_pool_dns_domain_name = oke_config.value["node_pool_dns_domain_name"]
      # node_pool_subnet_name - (optional) is a type of string
      node_pool_subnet_name = oke_config.value["node_pool_subnet_name"]
      # node_public_key_contents - (optional) is a type of string
      node_public_key_contents = oke_config.value["node_public_key_contents"]
      # node_shape - (required) is a type of string
      node_shape = oke_config.value["node_shape"]
      # private_key_contents - (required) is a type of string
      private_key_contents = oke_config.value["private_key_contents"]
      # private_key_passphrase - (optional) is a type of string
      private_key_passphrase = oke_config.value["private_key_passphrase"]
      # quantity_of_node_subnets - (optional) is a type of number
      quantity_of_node_subnets = oke_config.value["quantity_of_node_subnets"]
      # quantity_per_subnet - (optional) is a type of number
      quantity_per_subnet = oke_config.value["quantity_per_subnet"]
      # region - (required) is a type of string
      region = oke_config.value["region"]
      # service_dns_domain_name - (optional) is a type of string
      service_dns_domain_name = oke_config.value["service_dns_domain_name"]
      # skip_vcn_delete - (optional) is a type of bool
      skip_vcn_delete = oke_config.value["skip_vcn_delete"]
      # tenancy_id - (required) is a type of string
      tenancy_id = oke_config.value["tenancy_id"]
      # user_ocid - (required) is a type of string
      user_ocid = oke_config.value["user_ocid"]
      # vcn_compartment_id - (optional) is a type of string
      vcn_compartment_id = oke_config.value["vcn_compartment_id"]
      # vcn_name - (optional) is a type of string
      vcn_name = oke_config.value["vcn_name"]
      # worker_node_ingress_cidr - (optional) is a type of string
      worker_node_ingress_cidr = oke_config.value["worker_node_ingress_cidr"]
    }
  }

  dynamic "rke_config" {
    for_each = var.rke_config
    content {
      # addon_job_timeout - (optional) is a type of number
      addon_job_timeout = rke_config.value["addon_job_timeout"]
      # addons - (optional) is a type of string
      addons = rke_config.value["addons"]
      # addons_include - (optional) is a type of list of string
      addons_include = rke_config.value["addons_include"]
      # ignore_docker_version - (optional) is a type of bool
      ignore_docker_version = rke_config.value["ignore_docker_version"]
      # kubernetes_version - (optional) is a type of string
      kubernetes_version = rke_config.value["kubernetes_version"]
      # prefix_path - (optional) is a type of string
      prefix_path = rke_config.value["prefix_path"]
      # ssh_agent_auth - (optional) is a type of bool
      ssh_agent_auth = rke_config.value["ssh_agent_auth"]
      # ssh_cert_path - (optional) is a type of string
      ssh_cert_path = rke_config.value["ssh_cert_path"]
      # ssh_key_path - (optional) is a type of string
      ssh_key_path = rke_config.value["ssh_key_path"]
      # win_prefix_path - (optional) is a type of string
      win_prefix_path = rke_config.value["win_prefix_path"]

      dynamic "authentication" {
        for_each = rke_config.value.authentication
        content {
          # sans - (optional) is a type of list of string
          sans = authentication.value["sans"]
          # strategy - (optional) is a type of string
          strategy = authentication.value["strategy"]
        }
      }

      dynamic "authorization" {
        for_each = rke_config.value.authorization
        content {
          # mode - (optional) is a type of string
          mode = authorization.value["mode"]
          # options - (optional) is a type of map of string
          options = authorization.value["options"]
        }
      }

      dynamic "bastion_host" {
        for_each = rke_config.value.bastion_host
        content {
          # address - (required) is a type of string
          address = bastion_host.value["address"]
          # port - (optional) is a type of string
          port = bastion_host.value["port"]
          # ssh_agent_auth - (optional) is a type of bool
          ssh_agent_auth = bastion_host.value["ssh_agent_auth"]
          # ssh_key - (optional) is a type of string
          ssh_key = bastion_host.value["ssh_key"]
          # ssh_key_path - (optional) is a type of string
          ssh_key_path = bastion_host.value["ssh_key_path"]
          # user - (required) is a type of string
          user = bastion_host.value["user"]
        }
      }

      dynamic "cloud_provider" {
        for_each = rke_config.value.cloud_provider
        content {
          # custom_cloud_provider - (optional) is a type of string
          custom_cloud_provider = cloud_provider.value["custom_cloud_provider"]
          # name - (optional) is a type of string
          name = cloud_provider.value["name"]

          dynamic "aws_cloud_provider" {
            for_each = cloud_provider.value.aws_cloud_provider
            content {

              dynamic "global" {
                for_each = aws_cloud_provider.value.global
                content {
                  # disable_security_group_ingress - (optional) is a type of bool
                  disable_security_group_ingress = global.value["disable_security_group_ingress"]
                  # disable_strict_zone_check - (optional) is a type of bool
                  disable_strict_zone_check = global.value["disable_strict_zone_check"]
                  # elb_security_group - (optional) is a type of string
                  elb_security_group = global.value["elb_security_group"]
                  # kubernetes_cluster_id - (optional) is a type of string
                  kubernetes_cluster_id = global.value["kubernetes_cluster_id"]
                  # kubernetes_cluster_tag - (optional) is a type of string
                  kubernetes_cluster_tag = global.value["kubernetes_cluster_tag"]
                  # role_arn - (optional) is a type of string
                  role_arn = global.value["role_arn"]
                  # route_table_id - (optional) is a type of string
                  route_table_id = global.value["route_table_id"]
                  # subnet_id - (optional) is a type of string
                  subnet_id = global.value["subnet_id"]
                  # vpc - (optional) is a type of string
                  vpc = global.value["vpc"]
                  # zone - (optional) is a type of string
                  zone = global.value["zone"]
                }
              }

              dynamic "service_override" {
                for_each = aws_cloud_provider.value.service_override
                content {
                  # region - (optional) is a type of string
                  region = service_override.value["region"]
                  # service - (required) is a type of string
                  service = service_override.value["service"]
                  # signing_method - (optional) is a type of string
                  signing_method = service_override.value["signing_method"]
                  # signing_name - (optional) is a type of string
                  signing_name = service_override.value["signing_name"]
                  # signing_region - (optional) is a type of string
                  signing_region = service_override.value["signing_region"]
                  # url - (optional) is a type of string
                  url = service_override.value["url"]
                }
              }

            }
          }

          dynamic "azure_cloud_provider" {
            for_each = cloud_provider.value.azure_cloud_provider
            content {
              # aad_client_cert_password - (optional) is a type of string
              aad_client_cert_password = azure_cloud_provider.value["aad_client_cert_password"]
              # aad_client_cert_path - (optional) is a type of string
              aad_client_cert_path = azure_cloud_provider.value["aad_client_cert_path"]
              # aad_client_id - (required) is a type of string
              aad_client_id = azure_cloud_provider.value["aad_client_id"]
              # aad_client_secret - (required) is a type of string
              aad_client_secret = azure_cloud_provider.value["aad_client_secret"]
              # cloud - (optional) is a type of string
              cloud = azure_cloud_provider.value["cloud"]
              # cloud_provider_backoff - (optional) is a type of bool
              cloud_provider_backoff = azure_cloud_provider.value["cloud_provider_backoff"]
              # cloud_provider_backoff_duration - (optional) is a type of number
              cloud_provider_backoff_duration = azure_cloud_provider.value["cloud_provider_backoff_duration"]
              # cloud_provider_backoff_exponent - (optional) is a type of number
              cloud_provider_backoff_exponent = azure_cloud_provider.value["cloud_provider_backoff_exponent"]
              # cloud_provider_backoff_jitter - (optional) is a type of number
              cloud_provider_backoff_jitter = azure_cloud_provider.value["cloud_provider_backoff_jitter"]
              # cloud_provider_backoff_retries - (optional) is a type of number
              cloud_provider_backoff_retries = azure_cloud_provider.value["cloud_provider_backoff_retries"]
              # cloud_provider_rate_limit - (optional) is a type of bool
              cloud_provider_rate_limit = azure_cloud_provider.value["cloud_provider_rate_limit"]
              # cloud_provider_rate_limit_bucket - (optional) is a type of number
              cloud_provider_rate_limit_bucket = azure_cloud_provider.value["cloud_provider_rate_limit_bucket"]
              # cloud_provider_rate_limit_qps - (optional) is a type of number
              cloud_provider_rate_limit_qps = azure_cloud_provider.value["cloud_provider_rate_limit_qps"]
              # load_balancer_sku - (optional) is a type of string
              load_balancer_sku = azure_cloud_provider.value["load_balancer_sku"]
              # location - (optional) is a type of string
              location = azure_cloud_provider.value["location"]
              # maximum_load_balancer_rule_count - (optional) is a type of number
              maximum_load_balancer_rule_count = azure_cloud_provider.value["maximum_load_balancer_rule_count"]
              # primary_availability_set_name - (optional) is a type of string
              primary_availability_set_name = azure_cloud_provider.value["primary_availability_set_name"]
              # primary_scale_set_name - (optional) is a type of string
              primary_scale_set_name = azure_cloud_provider.value["primary_scale_set_name"]
              # resource_group - (optional) is a type of string
              resource_group = azure_cloud_provider.value["resource_group"]
              # route_table_name - (optional) is a type of string
              route_table_name = azure_cloud_provider.value["route_table_name"]
              # security_group_name - (optional) is a type of string
              security_group_name = azure_cloud_provider.value["security_group_name"]
              # subnet_name - (optional) is a type of string
              subnet_name = azure_cloud_provider.value["subnet_name"]
              # subscription_id - (required) is a type of string
              subscription_id = azure_cloud_provider.value["subscription_id"]
              # tenant_id - (required) is a type of string
              tenant_id = azure_cloud_provider.value["tenant_id"]
              # use_instance_metadata - (optional) is a type of bool
              use_instance_metadata = azure_cloud_provider.value["use_instance_metadata"]
              # use_managed_identity_extension - (optional) is a type of bool
              use_managed_identity_extension = azure_cloud_provider.value["use_managed_identity_extension"]
              # vm_type - (optional) is a type of string
              vm_type = azure_cloud_provider.value["vm_type"]
              # vnet_name - (optional) is a type of string
              vnet_name = azure_cloud_provider.value["vnet_name"]
              # vnet_resource_group - (optional) is a type of string
              vnet_resource_group = azure_cloud_provider.value["vnet_resource_group"]
            }
          }

          dynamic "openstack_cloud_provider" {
            for_each = cloud_provider.value.openstack_cloud_provider
            content {

              dynamic "block_storage" {
                for_each = openstack_cloud_provider.value.block_storage
                content {
                  # bs_version - (optional) is a type of string
                  bs_version = block_storage.value["bs_version"]
                  # ignore_volume_az - (optional) is a type of bool
                  ignore_volume_az = block_storage.value["ignore_volume_az"]
                  # trust_device_path - (optional) is a type of bool
                  trust_device_path = block_storage.value["trust_device_path"]
                }
              }

              dynamic "global" {
                for_each = openstack_cloud_provider.value.global
                content {
                  # auth_url - (required) is a type of string
                  auth_url = global.value["auth_url"]
                  # ca_file - (optional) is a type of string
                  ca_file = global.value["ca_file"]
                  # domain_id - (optional) is a type of string
                  domain_id = global.value["domain_id"]
                  # domain_name - (optional) is a type of string
                  domain_name = global.value["domain_name"]
                  # password - (required) is a type of string
                  password = global.value["password"]
                  # region - (optional) is a type of string
                  region = global.value["region"]
                  # tenant_id - (optional) is a type of string
                  tenant_id = global.value["tenant_id"]
                  # tenant_name - (optional) is a type of string
                  tenant_name = global.value["tenant_name"]
                  # trust_id - (optional) is a type of string
                  trust_id = global.value["trust_id"]
                  # username - (required) is a type of string
                  username = global.value["username"]
                }
              }

              dynamic "load_balancer" {
                for_each = openstack_cloud_provider.value.load_balancer
                content {
                  # create_monitor - (optional) is a type of bool
                  create_monitor = load_balancer.value["create_monitor"]
                  # floating_network_id - (optional) is a type of string
                  floating_network_id = load_balancer.value["floating_network_id"]
                  # lb_method - (optional) is a type of string
                  lb_method = load_balancer.value["lb_method"]
                  # lb_provider - (optional) is a type of string
                  lb_provider = load_balancer.value["lb_provider"]
                  # lb_version - (optional) is a type of string
                  lb_version = load_balancer.value["lb_version"]
                  # manage_security_groups - (optional) is a type of bool
                  manage_security_groups = load_balancer.value["manage_security_groups"]
                  # monitor_delay - (optional) is a type of string
                  monitor_delay = load_balancer.value["monitor_delay"]
                  # monitor_max_retries - (optional) is a type of number
                  monitor_max_retries = load_balancer.value["monitor_max_retries"]
                  # monitor_timeout - (optional) is a type of string
                  monitor_timeout = load_balancer.value["monitor_timeout"]
                  # subnet_id - (optional) is a type of string
                  subnet_id = load_balancer.value["subnet_id"]
                  # use_octavia - (optional) is a type of bool
                  use_octavia = load_balancer.value["use_octavia"]
                }
              }

              dynamic "metadata" {
                for_each = openstack_cloud_provider.value.metadata
                content {
                  # request_timeout - (optional) is a type of number
                  request_timeout = metadata.value["request_timeout"]
                  # search_order - (optional) is a type of string
                  search_order = metadata.value["search_order"]
                }
              }

              dynamic "route" {
                for_each = openstack_cloud_provider.value.route
                content {
                  # router_id - (optional) is a type of string
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
                  # scsi_controller_type - (optional) is a type of string
                  scsi_controller_type = disk.value["scsi_controller_type"]
                }
              }

              dynamic "global" {
                for_each = vsphere_cloud_provider.value.global
                content {
                  # datacenters - (optional) is a type of string
                  datacenters = global.value["datacenters"]
                  # insecure_flag - (optional) is a type of bool
                  insecure_flag = global.value["insecure_flag"]
                  # password - (optional) is a type of string
                  password = global.value["password"]
                  # port - (optional) is a type of string
                  port = global.value["port"]
                  # soap_roundtrip_count - (optional) is a type of number
                  soap_roundtrip_count = global.value["soap_roundtrip_count"]
                  # user - (optional) is a type of string
                  user = global.value["user"]
                }
              }

              dynamic "network" {
                for_each = vsphere_cloud_provider.value.network
                content {
                  # public_network - (optional) is a type of string
                  public_network = network.value["public_network"]
                }
              }

              dynamic "virtual_center" {
                for_each = vsphere_cloud_provider.value.virtual_center
                content {
                  # datacenters - (required) is a type of string
                  datacenters = virtual_center.value["datacenters"]
                  # name - (required) is a type of string
                  name = virtual_center.value["name"]
                  # password - (required) is a type of string
                  password = virtual_center.value["password"]
                  # port - (optional) is a type of string
                  port = virtual_center.value["port"]
                  # soap_roundtrip_count - (optional) is a type of number
                  soap_roundtrip_count = virtual_center.value["soap_roundtrip_count"]
                  # user - (required) is a type of string
                  user = virtual_center.value["user"]
                }
              }

              dynamic "workspace" {
                for_each = vsphere_cloud_provider.value.workspace
                content {
                  # datacenter - (required) is a type of string
                  datacenter = workspace.value["datacenter"]
                  # default_datastore - (optional) is a type of string
                  default_datastore = workspace.value["default_datastore"]
                  # folder - (required) is a type of string
                  folder = workspace.value["folder"]
                  # resourcepool_path - (optional) is a type of string
                  resourcepool_path = workspace.value["resourcepool_path"]
                  # server - (required) is a type of string
                  server = workspace.value["server"]
                }
              }

            }
          }

        }
      }

      dynamic "dns" {
        for_each = rke_config.value.dns
        content {
          # node_selector - (optional) is a type of map of string
          node_selector = dns.value["node_selector"]
          # provider - (optional) is a type of string
          provider = dns.value["provider"]
          # reverse_cidrs - (optional) is a type of list of string
          reverse_cidrs = dns.value["reverse_cidrs"]
          # upstream_nameservers - (optional) is a type of list of string
          upstream_nameservers = dns.value["upstream_nameservers"]

          dynamic "linear_autoscaler_params" {
            for_each = dns.value.linear_autoscaler_params
            content {
              # cores_per_replica - (optional) is a type of number
              cores_per_replica = linear_autoscaler_params.value["cores_per_replica"]
              # max - (optional) is a type of number
              max = linear_autoscaler_params.value["max"]
              # min - (optional) is a type of number
              min = linear_autoscaler_params.value["min"]
              # nodes_per_replica - (optional) is a type of number
              nodes_per_replica = linear_autoscaler_params.value["nodes_per_replica"]
              # prevent_single_point_failure - (optional) is a type of bool
              prevent_single_point_failure = linear_autoscaler_params.value["prevent_single_point_failure"]
            }
          }

          dynamic "nodelocal" {
            for_each = dns.value.nodelocal
            content {
              # ip_address - (optional) is a type of string
              ip_address = nodelocal.value["ip_address"]
              # node_selector - (optional) is a type of map of string
              node_selector = nodelocal.value["node_selector"]
            }
          }

          dynamic "update_strategy" {
            for_each = dns.value.update_strategy
            content {
              # strategy - (optional) is a type of string
              strategy = update_strategy.value["strategy"]

              dynamic "rolling_update" {
                for_each = update_strategy.value.rolling_update
                content {
                  # max_surge - (optional) is a type of number
                  max_surge = rolling_update.value["max_surge"]
                  # max_unavailable - (optional) is a type of number
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
          # dns_policy - (optional) is a type of string
          dns_policy = ingress.value["dns_policy"]
          # extra_args - (optional) is a type of map of string
          extra_args = ingress.value["extra_args"]
          # node_selector - (optional) is a type of map of string
          node_selector = ingress.value["node_selector"]
          # options - (optional) is a type of map of string
          options = ingress.value["options"]
          # provider - (optional) is a type of string
          provider = ingress.value["provider"]
        }
      }

      dynamic "monitoring" {
        for_each = rke_config.value.monitoring
        content {
          # node_selector - (optional) is a type of map of string
          node_selector = monitoring.value["node_selector"]
          # options - (optional) is a type of map of string
          options = monitoring.value["options"]
          # provider - (optional) is a type of string
          provider = monitoring.value["provider"]
          # replicas - (optional) is a type of number
          replicas = monitoring.value["replicas"]

          dynamic "update_strategy" {
            for_each = monitoring.value.update_strategy
            content {
              # strategy - (optional) is a type of string
              strategy = update_strategy.value["strategy"]

              dynamic "rolling_update" {
                for_each = update_strategy.value.rolling_update
                content {
                  # max_surge - (optional) is a type of number
                  max_surge = rolling_update.value["max_surge"]
                  # max_unavailable - (optional) is a type of number
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
          # mtu - (optional) is a type of number
          mtu = network.value["mtu"]
          # options - (optional) is a type of map of string
          options = network.value["options"]
          # plugin - (optional) is a type of string
          plugin = network.value["plugin"]

          dynamic "calico_network_provider" {
            for_each = network.value.calico_network_provider
            content {
              # cloud_provider - (optional) is a type of string
              cloud_provider = calico_network_provider.value["cloud_provider"]
            }
          }

          dynamic "canal_network_provider" {
            for_each = network.value.canal_network_provider
            content {
              # iface - (optional) is a type of string
              iface = canal_network_provider.value["iface"]
            }
          }

          dynamic "flannel_network_provider" {
            for_each = network.value.flannel_network_provider
            content {
              # iface - (optional) is a type of string
              iface = flannel_network_provider.value["iface"]
            }
          }

          dynamic "weave_network_provider" {
            for_each = network.value.weave_network_provider
            content {
              # password - (required) is a type of string
              password = weave_network_provider.value["password"]
            }
          }

        }
      }

      dynamic "nodes" {
        for_each = rke_config.value.nodes
        content {
          # address - (required) is a type of string
          address = nodes.value["address"]
          # docker_socket - (optional) is a type of string
          docker_socket = nodes.value["docker_socket"]
          # hostname_override - (optional) is a type of string
          hostname_override = nodes.value["hostname_override"]
          # internal_address - (optional) is a type of string
          internal_address = nodes.value["internal_address"]
          # labels - (optional) is a type of map of string
          labels = nodes.value["labels"]
          # node_id - (optional) is a type of string
          node_id = nodes.value["node_id"]
          # port - (optional) is a type of string
          port = nodes.value["port"]
          # role - (required) is a type of list of string
          role = nodes.value["role"]
          # ssh_agent_auth - (optional) is a type of bool
          ssh_agent_auth = nodes.value["ssh_agent_auth"]
          # ssh_key - (optional) is a type of string
          ssh_key = nodes.value["ssh_key"]
          # ssh_key_path - (optional) is a type of string
          ssh_key_path = nodes.value["ssh_key_path"]
          # user - (required) is a type of string
          user = nodes.value["user"]
        }
      }

      dynamic "private_registries" {
        for_each = rke_config.value.private_registries
        content {
          # is_default - (optional) is a type of bool
          is_default = private_registries.value["is_default"]
          # password - (optional) is a type of string
          password = private_registries.value["password"]
          # url - (required) is a type of string
          url = private_registries.value["url"]
          # user - (optional) is a type of string
          user = private_registries.value["user"]
        }
      }

      dynamic "services" {
        for_each = rke_config.value.services
        content {

          dynamic "etcd" {
            for_each = services.value.etcd
            content {
              # ca_cert - (optional) is a type of string
              ca_cert = etcd.value["ca_cert"]
              # cert - (optional) is a type of string
              cert = etcd.value["cert"]
              # creation - (optional) is a type of string
              creation = etcd.value["creation"]
              # external_urls - (optional) is a type of list of string
              external_urls = etcd.value["external_urls"]
              # extra_args - (optional) is a type of map of string
              extra_args = etcd.value["extra_args"]
              # extra_binds - (optional) is a type of list of string
              extra_binds = etcd.value["extra_binds"]
              # extra_env - (optional) is a type of list of string
              extra_env = etcd.value["extra_env"]
              # gid - (optional) is a type of number
              gid = etcd.value["gid"]
              # image - (optional) is a type of string
              image = etcd.value["image"]
              # key - (optional) is a type of string
              key = etcd.value["key"]
              # path - (optional) is a type of string
              path = etcd.value["path"]
              # retention - (optional) is a type of string
              retention = etcd.value["retention"]
              # snapshot - (optional) is a type of bool
              snapshot = etcd.value["snapshot"]
              # uid - (optional) is a type of number
              uid = etcd.value["uid"]

              dynamic "backup_config" {
                for_each = etcd.value.backup_config
                content {
                  # enabled - (optional) is a type of bool
                  enabled = backup_config.value["enabled"]
                  # interval_hours - (optional) is a type of number
                  interval_hours = backup_config.value["interval_hours"]
                  # retention - (optional) is a type of number
                  retention = backup_config.value["retention"]
                  # safe_timestamp - (optional) is a type of bool
                  safe_timestamp = backup_config.value["safe_timestamp"]
                  # timeout - (optional) is a type of number
                  timeout = backup_config.value["timeout"]

                  dynamic "s3_backup_config" {
                    for_each = backup_config.value.s3_backup_config
                    content {
                      # access_key - (optional) is a type of string
                      access_key = s3_backup_config.value["access_key"]
                      # bucket_name - (required) is a type of string
                      bucket_name = s3_backup_config.value["bucket_name"]
                      # custom_ca - (optional) is a type of string
                      custom_ca = s3_backup_config.value["custom_ca"]
                      # endpoint - (required) is a type of string
                      endpoint = s3_backup_config.value["endpoint"]
                      # folder - (optional) is a type of string
                      folder = s3_backup_config.value["folder"]
                      # region - (optional) is a type of string
                      region = s3_backup_config.value["region"]
                      # secret_key - (optional) is a type of string
                      secret_key = s3_backup_config.value["secret_key"]
                    }
                  }

                }
              }

            }
          }

          dynamic "kube_api" {
            for_each = services.value.kube_api
            content {
              # admission_configuration - (optional) is a type of map of string
              admission_configuration = kube_api.value["admission_configuration"]
              # always_pull_images - (optional) is a type of bool
              always_pull_images = kube_api.value["always_pull_images"]
              # extra_args - (optional) is a type of map of string
              extra_args = kube_api.value["extra_args"]
              # extra_binds - (optional) is a type of list of string
              extra_binds = kube_api.value["extra_binds"]
              # extra_env - (optional) is a type of list of string
              extra_env = kube_api.value["extra_env"]
              # image - (optional) is a type of string
              image = kube_api.value["image"]
              # pod_security_policy - (optional) is a type of bool
              pod_security_policy = kube_api.value["pod_security_policy"]
              # service_cluster_ip_range - (optional) is a type of string
              service_cluster_ip_range = kube_api.value["service_cluster_ip_range"]
              # service_node_port_range - (optional) is a type of string
              service_node_port_range = kube_api.value["service_node_port_range"]

              dynamic "audit_log" {
                for_each = kube_api.value.audit_log
                content {
                  # enabled - (optional) is a type of bool
                  enabled = audit_log.value["enabled"]

                  dynamic "configuration" {
                    for_each = audit_log.value.configuration
                    content {
                      # format - (optional) is a type of string
                      format = configuration.value["format"]
                      # max_age - (optional) is a type of number
                      max_age = configuration.value["max_age"]
                      # max_backup - (optional) is a type of number
                      max_backup = configuration.value["max_backup"]
                      # max_size - (optional) is a type of number
                      max_size = configuration.value["max_size"]
                      # path - (optional) is a type of string
                      path = configuration.value["path"]
                      # policy - (optional) is a type of string
                      policy = configuration.value["policy"]
                    }
                  }

                }
              }

              dynamic "event_rate_limit" {
                for_each = kube_api.value.event_rate_limit
                content {
                  # configuration - (optional) is a type of string
                  configuration = event_rate_limit.value["configuration"]
                  # enabled - (optional) is a type of bool
                  enabled = event_rate_limit.value["enabled"]
                }
              }

              dynamic "secrets_encryption_config" {
                for_each = kube_api.value.secrets_encryption_config
                content {
                  # custom_config - (optional) is a type of string
                  custom_config = secrets_encryption_config.value["custom_config"]
                  # enabled - (optional) is a type of bool
                  enabled = secrets_encryption_config.value["enabled"]
                }
              }

            }
          }

          dynamic "kube_controller" {
            for_each = services.value.kube_controller
            content {
              # cluster_cidr - (optional) is a type of string
              cluster_cidr = kube_controller.value["cluster_cidr"]
              # extra_args - (optional) is a type of map of string
              extra_args = kube_controller.value["extra_args"]
              # extra_binds - (optional) is a type of list of string
              extra_binds = kube_controller.value["extra_binds"]
              # extra_env - (optional) is a type of list of string
              extra_env = kube_controller.value["extra_env"]
              # image - (optional) is a type of string
              image = kube_controller.value["image"]
              # service_cluster_ip_range - (optional) is a type of string
              service_cluster_ip_range = kube_controller.value["service_cluster_ip_range"]
            }
          }

          dynamic "kubelet" {
            for_each = services.value.kubelet
            content {
              # cluster_dns_server - (optional) is a type of string
              cluster_dns_server = kubelet.value["cluster_dns_server"]
              # cluster_domain - (optional) is a type of string
              cluster_domain = kubelet.value["cluster_domain"]
              # extra_args - (optional) is a type of map of string
              extra_args = kubelet.value["extra_args"]
              # extra_binds - (optional) is a type of list of string
              extra_binds = kubelet.value["extra_binds"]
              # extra_env - (optional) is a type of list of string
              extra_env = kubelet.value["extra_env"]
              # fail_swap_on - (optional) is a type of bool
              fail_swap_on = kubelet.value["fail_swap_on"]
              # generate_serving_certificate - (optional) is a type of bool
              generate_serving_certificate = kubelet.value["generate_serving_certificate"]
              # image - (optional) is a type of string
              image = kubelet.value["image"]
              # infra_container_image - (optional) is a type of string
              infra_container_image = kubelet.value["infra_container_image"]
            }
          }

          dynamic "kubeproxy" {
            for_each = services.value.kubeproxy
            content {
              # extra_args - (optional) is a type of map of string
              extra_args = kubeproxy.value["extra_args"]
              # extra_binds - (optional) is a type of list of string
              extra_binds = kubeproxy.value["extra_binds"]
              # extra_env - (optional) is a type of list of string
              extra_env = kubeproxy.value["extra_env"]
              # image - (optional) is a type of string
              image = kubeproxy.value["image"]
            }
          }

          dynamic "scheduler" {
            for_each = services.value.scheduler
            content {
              # extra_args - (optional) is a type of map of string
              extra_args = scheduler.value["extra_args"]
              # extra_binds - (optional) is a type of list of string
              extra_binds = scheduler.value["extra_binds"]
              # extra_env - (optional) is a type of list of string
              extra_env = scheduler.value["extra_env"]
              # image - (optional) is a type of string
              image = scheduler.value["image"]
            }
          }

        }
      }

      dynamic "upgrade_strategy" {
        for_each = rke_config.value.upgrade_strategy
        content {
          # drain - (optional) is a type of bool
          drain = upgrade_strategy.value["drain"]
          # max_unavailable_controlplane - (optional) is a type of string
          max_unavailable_controlplane = upgrade_strategy.value["max_unavailable_controlplane"]
          # max_unavailable_worker - (optional) is a type of string
          max_unavailable_worker = upgrade_strategy.value["max_unavailable_worker"]

          dynamic "drain_input" {
            for_each = upgrade_strategy.value.drain_input
            content {
              # delete_local_data - (optional) is a type of bool
              delete_local_data = drain_input.value["delete_local_data"]
              # force - (optional) is a type of bool
              force = drain_input.value["force"]
              # grace_period - (optional) is a type of number
              grace_period = drain_input.value["grace_period"]
              # ignore_daemon_sets - (optional) is a type of bool
              ignore_daemon_sets = drain_input.value["ignore_daemon_sets"]
              # timeout - (optional) is a type of number
              timeout = drain_input.value["timeout"]
            }
          }

        }
      }

    }
  }

  dynamic "scheduled_cluster_scan" {
    for_each = var.scheduled_cluster_scan
    content {
      # enabled - (optional) is a type of bool
      enabled = scheduled_cluster_scan.value["enabled"]

      dynamic "scan_config" {
        for_each = scheduled_cluster_scan.value.scan_config
        content {

          dynamic "cis_scan_config" {
            for_each = scan_config.value.cis_scan_config
            content {
              # debug_master - (optional) is a type of bool
              debug_master = cis_scan_config.value["debug_master"]
              # debug_worker - (optional) is a type of bool
              debug_worker = cis_scan_config.value["debug_worker"]
              # override_benchmark_version - (optional) is a type of string
              override_benchmark_version = cis_scan_config.value["override_benchmark_version"]
              # override_skip - (optional) is a type of list of string
              override_skip = cis_scan_config.value["override_skip"]
              # profile - (optional) is a type of string
              profile = cis_scan_config.value["profile"]
            }
          }

        }
      }

      dynamic "schedule_config" {
        for_each = scheduled_cluster_scan.value.schedule_config
        content {
          # cron_schedule - (required) is a type of string
          cron_schedule = schedule_config.value["cron_schedule"]
          # retention - (optional) is a type of number
          retention = schedule_config.value["retention"]
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
output "annotations" {
  description = "returns a map of string"
  value       = rancher2_cluster.this.annotations
}

output "ca_cert" {
  description = "returns a string"
  value       = rancher2_cluster.this.ca_cert
  sensitive   = true
}

output "cluster_registration_token" {
  description = "returns a list of object"
  value       = rancher2_cluster.this.cluster_registration_token
}

output "default_pod_security_policy_template_id" {
  description = "returns a string"
  value       = rancher2_cluster.this.default_pod_security_policy_template_id
}

output "default_project_id" {
  description = "returns a string"
  value       = rancher2_cluster.this.default_project_id
}

output "desired_agent_image" {
  description = "returns a string"
  value       = rancher2_cluster.this.desired_agent_image
}

output "desired_auth_image" {
  description = "returns a string"
  value       = rancher2_cluster.this.desired_auth_image
}

output "docker_root_dir" {
  description = "returns a string"
  value       = rancher2_cluster.this.docker_root_dir
}

output "driver" {
  description = "returns a string"
  value       = rancher2_cluster.this.driver
}

output "enable_cluster_alerting" {
  description = "returns a bool"
  value       = rancher2_cluster.this.enable_cluster_alerting
}

output "enable_cluster_istio" {
  description = "returns a bool"
  value       = rancher2_cluster.this.enable_cluster_istio
}

output "enable_cluster_monitoring" {
  description = "returns a bool"
  value       = rancher2_cluster.this.enable_cluster_monitoring
}

output "enable_network_policy" {
  description = "returns a bool"
  value       = rancher2_cluster.this.enable_network_policy
}

output "id" {
  description = "returns a string"
  value       = rancher2_cluster.this.id
}

output "istio_enabled" {
  description = "returns a bool"
  value       = rancher2_cluster.this.istio_enabled
}

output "kube_config" {
  description = "returns a string"
  value       = rancher2_cluster.this.kube_config
  sensitive   = true
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_cluster.this.labels
}

output "system_project_id" {
  description = "returns a string"
  value       = rancher2_cluster.this.system_project_id
}

output "this" {
  value = rancher2_cluster.this
}
```

[top](#index)