# avi_cloud

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_cloud" {
  source = "./modules/avi/r/avi_cloud"

  # apic_mode - (optional) is a type of bool
  apic_mode = null
  # autoscale_polling_interval - (optional) is a type of number
  autoscale_polling_interval = null
  # dhcp_enabled - (optional) is a type of bool
  dhcp_enabled = null
  # dns_provider_ref - (optional) is a type of string
  dns_provider_ref = null
  # dns_resolution_on_se - (optional) is a type of bool
  dns_resolution_on_se = null
  # east_west_dns_provider_ref - (optional) is a type of string
  east_west_dns_provider_ref = null
  # east_west_ipam_provider_ref - (optional) is a type of string
  east_west_ipam_provider_ref = null
  # enable_vip_on_all_interfaces - (optional) is a type of bool
  enable_vip_on_all_interfaces = null
  # enable_vip_static_routes - (optional) is a type of bool
  enable_vip_static_routes = null
  # ip6_autocfg_enabled - (optional) is a type of bool
  ip6_autocfg_enabled = null
  # ipam_provider_ref - (optional) is a type of string
  ipam_provider_ref = null
  # license_tier - (optional) is a type of string
  license_tier = null
  # license_type - (optional) is a type of string
  license_type = null
  # mtu - (optional) is a type of number
  mtu = null
  # name - (required) is a type of string
  name = null
  # obj_name_prefix - (optional) is a type of string
  obj_name_prefix = null
  # prefer_static_routes - (optional) is a type of bool
  prefer_static_routes = null
  # se_group_template_ref - (optional) is a type of string
  se_group_template_ref = null
  # state_based_dns_registration - (optional) is a type of bool
  state_based_dns_registration = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
  # vtype - (required) is a type of string
  vtype = null

  apic_configuration = [{
    apic_admin_tenant = null
    apic_domain       = null
    apic_name         = []
    apic_password     = null
    apic_username     = null
    context_aware     = null
    se_tunnel_mode    = null
  }]

  aws_configuration = [{
    access_key_id     = null
    asg_poll_interval = null
    ebs_encryption = [{
      master_key = null
      mode       = null
    }]
    free_elasticips            = null
    iam_assume_role            = null
    publish_vip_to_public_zone = null
    region                     = null
    route53_integration        = null
    s3_encryption = [{
      master_key = null
      mode       = null
    }]
    secret_access_key = null
    sqs_encryption = [{
      master_key = null
      mode       = null
    }]
    ttl           = null
    use_iam_roles = null
    use_sns_sqs   = null
    vpc           = null
    vpc_id        = null
    zones = [{
      availability_zone = null
      mgmt_network_name = null
      mgmt_network_uuid = null
    }]
  }]

  azure_configuration = [{
    availability_zones    = []
    cloud_credentials_ref = null
    location              = null
    network_info = [{
      management_network_id = null
      se_network_id         = null
      virtual_network_id    = null
    }]
    resource_group    = null
    subscription_id   = null
    use_azure_dns     = null
    use_enhanced_ha   = null
    use_managed_disks = null
    use_standard_alb  = null
  }]

  cloudstack_configuration = [{
    access_key_id     = null
    api_url           = null
    cntr_public_ip    = null
    hypervisor        = null
    mgmt_network_name = null
    mgmt_network_uuid = null
    secret_access_key = null
  }]

  custom_tags = [{
    tag_key = null
    tag_val = null
  }]

  docker_configuration = [{
    app_sync_frequency                 = null
    ca_tls_key_and_certificate_ref     = null
    client_tls_key_and_certificate_ref = null
    container_port_match_http_service  = null
    coredump_directory                 = null
    disable_auto_backend_service_sync  = null
    disable_auto_frontend_service_sync = null
    disable_auto_se_creation           = null
    docker_registry_se = [{
      oshift_registry = [{
        registry_namespace = null
        registry_service   = null
        registry_vip = [{
          addr = null
          type = null
        }]
      }]
      password = null
      private  = null
      registry = null
      username = null
    }]
    east_west_placement_subnet = [{
      ip_addr = [{
        addr = null
        type = null
      }]
      mask = null
    }]
    enable_event_subscription         = null
    feproxy_container_port_as_service = null
    feproxy_vips_enable_proxy_arp     = null
    fleet_endpoint                    = null
    http_container_ports              = []
    se_deployment_method              = null
    se_exclude_attributes = [{
      attribute = null
      value     = null
    }]
    se_include_attributes = [{
      attribute = null
      value     = null
    }]
    se_spawn_rate                      = null
    se_volume                          = null
    services_accessible_all_interfaces = null
    ssh_user_ref                       = null
    ucp_nodes                          = []
    use_container_ip_port              = null
    use_controller_image               = null
  }]

  gcp_configuration = [{
    cloud_credentials_ref = null
    encryption_key_id     = null
    firewall_target_tags  = []
    gcs_bucket_name       = null
    gcs_project_id        = null
    network_config = [{
      config = null
      inband = [{
        vpc_network_name = null
        vpc_project_id   = null
        vpc_subnet_name  = null
      }]
      one_arm = [{
        data_vpc_network_name       = null
        data_vpc_project_id         = null
        data_vpc_subnet_name        = null
        management_vpc_network_name = null
        management_vpc_subnet_name  = null
      }]
      two_arm = [{
        backend_data_vpc_network_name  = null
        backend_data_vpc_subnet_name   = null
        frontend_data_vpc_network_name = null
        frontend_data_vpc_project_id   = null
        frontend_data_vpc_subnet_name  = null
        management_vpc_network_name    = null
        management_vpc_subnet_name     = null
      }]
    }]
    region_name   = null
    se_project_id = null
    vip_allocation_strategy = [{
      ilb = [{
        cloud_router_names = []
      }]
      mode = null
      routes = [{
        match_se_group_subnet = null
      }]
    }]
    zones = []
  }]

  linuxserver_configuration = [{
    hosts = [{
      host_attr = [{
        attr_key = null
        attr_val = null
      }]
      host_ip = [{
        addr = null
        type = null
      }]
      node_availability_zone = null
      se_group_ref           = null
    }]
    se_inband_mgmt      = null
    se_log_disk_path    = null
    se_log_disk_size_gb = null
    se_sys_disk_path    = null
    se_sys_disk_size_gb = null
    ssh_user_ref        = null
  }]

  nsx_configuration = [{
    avi_nsx_prefix       = null
    nsx_manager_name     = null
    nsx_manager_password = null
    nsx_manager_username = null
    nsx_poll_time        = null
  }]

  openstack_configuration = [{
    admin_tenant            = null
    admin_tenant_uuid       = null
    allowed_address_pairs   = null
    anti_affinity           = null
    auth_url                = null
    config_drive            = null
    contrail_disable_policy = null
    contrail_endpoint       = null
    contrail_plugin         = null
    custom_se_image_properties = [{
      name  = null
      value = null
    }]
    external_networks = null
    free_floatingips  = null
    hypervisor        = null
    hypervisor_properties = [{
      hypervisor = null
      image_properties = [{
        name  = null
        value = null
      }]
    }]
    img_format              = null
    import_keystone_tenants = null
    insecure                = null
    keystone_host           = null
    map_admin_to_cloudadmin = null
    mgmt_network_name       = null
    mgmt_network_uuid       = null
    name_owner              = null
    neutron_rbac            = null
    nuage_organization      = null
    nuage_password          = null
    nuage_port              = null
    nuage_username          = null
    nuage_virtualip         = null
    nuage_vsd_host          = null
    password                = null
    port_security           = null
    privilege               = null
    prov_name               = []
    provider_vip_networks = [{
      os_network_uuid = null
      os_tenant_uuids = []
    }]
    region = null
    role_mapping = [{
      avi_role = null
      os_role  = null
    }]
    security_groups        = null
    tenant_se              = null
    use_admin_url          = null
    use_internal_endpoints = null
    use_keystone_auth      = null
    use_nuagevip           = null
    username               = null
  }]

  oshiftk8s_configuration = [{
    app_sync_frequency = null
    auto_assign_fqdn   = null
    avi_bridge_subnet = [{
      ip_addr = [{
        addr = null
        type = null
      }]
      mask = null
    }]
    ca_tls_key_and_certificate_ref       = null
    client_tls_key_and_certificate_ref   = null
    cluster_tag                          = null
    container_port_match_http_service    = null
    coredump_directory                   = null
    default_service_as_east_west_service = null
    disable_auto_backend_service_sync    = null
    disable_auto_frontend_service_sync   = null
    disable_auto_gs_sync                 = null
    disable_auto_se_creation             = null
    docker_endpoint                      = null
    docker_registry_se = [{
      oshift_registry = [{
        registry_namespace = null
        registry_service   = null
        registry_vip = [{
          addr = null
          type = null
        }]
      }]
      password = null
      private  = null
      registry = null
      username = null
    }]
    east_west_placement_subnet = [{
      ip_addr = [{
        addr = null
        type = null
      }]
      mask = null
    }]
    enable_event_subscription      = null
    enable_route_ingress_hardening = null
    feproxy_vips_enable_proxy_arp  = null
    http_container_ports           = []
    ing_exclude_attributes = [{
      attribute = null
      value     = null
    }]
    ing_include_attributes = [{
      attribute = null
      value     = null
    }]
    l4_health_monitoring         = null
    master_nodes                 = []
    node_availability_zone_label = null
    ns_exclude_attributes = [{
      attribute = null
      value     = null
    }]
    ns_include_attributes = [{
      attribute = null
      value     = null
    }]
    num_shards              = null
    override_service_ports  = null
    persistent_volume_claim = null
    routes = [{
      if_name           = null
      network_namespace = null
      nexthop = [{
        addr = null
        type = null
      }]
      subnet = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
    }]
    sdn_overlay          = null
    se_deployment_method = null
    se_exclude_attributes = [{
      attribute = null
      value     = null
    }]
    se_image_pull_secret = null
    se_include_attributes = [{
      attribute = null
      value     = null
    }]
    se_namespace = null
    se_pod_tolerations = [{
      effect             = null
      key                = null
      operator           = null
      toleration_seconds = null
      value              = null
    }]
    se_priority_class                = null
    se_restart_batch_size            = null
    se_restart_force                 = null
    se_volume                        = null
    secure_egress_mode               = null
    service_account_token            = null
    shard_prefix                     = null
    shared_virtualservice_namespace  = null
    ssh_user_ref                     = null
    sync_not_ready_addresses         = null
    use_controller_image             = null
    use_resource_definition_as_ssot  = null
    use_scheduling_disabled_nodes    = null
    use_service_cluster_ip_as_ew_vip = null
    vip_default_gateway = [{
      addr = null
      type = null
    }]
  }]

  proxy_configuration = [{
    host     = null
    password = null
    port     = null
    username = null
  }]

  rancher_configuration = [{
    access_key                         = null
    app_sync_frequency                 = null
    container_port_match_http_service  = null
    coredump_directory                 = null
    disable_auto_backend_service_sync  = null
    disable_auto_frontend_service_sync = null
    disable_auto_se_creation           = null
    docker_registry_se = [{
      oshift_registry = [{
        registry_namespace = null
        registry_service   = null
        registry_vip = [{
          addr = null
          type = null
        }]
      }]
      password = null
      private  = null
      registry = null
      username = null
    }]
    east_west_placement_subnet = [{
      ip_addr = [{
        addr = null
        type = null
      }]
      mask = null
    }]
    enable_event_subscription         = null
    feproxy_container_port_as_service = null
    feproxy_vips_enable_proxy_arp     = null
    fleet_endpoint                    = null
    http_container_ports              = []
    nuage_controller = [{
      nuage_organization = null
      nuage_password     = null
      nuage_port         = null
      nuage_username     = null
      nuage_vsd_host     = null
      se_domain          = null
      se_enterprise      = null
      se_network         = null
      se_policy_group    = null
      se_user            = null
      se_zone            = null
    }]
    rancher_servers      = []
    se_deployment_method = null
    se_exclude_attributes = [{
      attribute = null
      value     = null
    }]
    se_include_attributes = [{
      attribute = null
      value     = null
    }]
    se_spawn_rate                      = null
    se_volume                          = null
    secret_key                         = null
    services_accessible_all_interfaces = null
    ssh_user_ref                       = null
    use_container_ip_port              = null
    use_controller_image               = null
  }]

  vca_configuration = [{
    privilege        = null
    vca_host         = null
    vca_instance     = null
    vca_mgmt_network = null
    vca_orgnization  = null
    vca_password     = null
    vca_username     = null
    vca_vdc          = null
  }]

  vcenter_configuration = [{
    datacenter = null
    management_ip_subnet = [{
      ip_addr = [{
        addr = null
        type = null
      }]
      mask = null
    }]
    management_network           = null
    password                     = null
    privilege                    = null
    username                     = null
    vcenter_template_se_location = null
    vcenter_url                  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "apic_mode" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "autoscale_polling_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dhcp_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "dns_provider_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_resolution_on_se" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "east_west_dns_provider_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "east_west_ipam_provider_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_vip_on_all_interfaces" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_vip_static_routes" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ip6_autocfg_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ipam_provider_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "license_tier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "license_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mtu" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "obj_name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "prefer_static_routes" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "se_group_template_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state_based_dns_registration" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vtype" {
  description = "(required)"
  type        = string
}

variable "apic_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      apic_admin_tenant = string
      apic_domain       = string
      apic_name         = list(string)
      apic_password     = string
      apic_username     = string
      context_aware     = string
      se_tunnel_mode    = bool
    }
  ))
  default = []
}

variable "aws_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access_key_id     = string
      asg_poll_interval = number
      ebs_encryption = set(object(
        {
          master_key = string
          mode       = string
        }
      ))
      free_elasticips            = bool
      iam_assume_role            = string
      publish_vip_to_public_zone = bool
      region                     = string
      route53_integration        = bool
      s3_encryption = set(object(
        {
          master_key = string
          mode       = string
        }
      ))
      secret_access_key = string
      sqs_encryption = set(object(
        {
          master_key = string
          mode       = string
        }
      ))
      ttl           = number
      use_iam_roles = bool
      use_sns_sqs   = bool
      vpc           = string
      vpc_id        = string
      zones = list(object(
        {
          availability_zone = string
          mgmt_network_name = string
          mgmt_network_uuid = string
        }
      ))
    }
  ))
  default = []
}

variable "azure_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      availability_zones    = list(string)
      cloud_credentials_ref = string
      location              = string
      network_info = list(object(
        {
          management_network_id = string
          se_network_id         = string
          virtual_network_id    = string
        }
      ))
      resource_group    = string
      subscription_id   = string
      use_azure_dns     = bool
      use_enhanced_ha   = bool
      use_managed_disks = bool
      use_standard_alb  = bool
    }
  ))
  default = []
}

variable "cloudstack_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access_key_id     = string
      api_url           = string
      cntr_public_ip    = string
      hypervisor        = string
      mgmt_network_name = string
      mgmt_network_uuid = string
      secret_access_key = string
    }
  ))
  default = []
}

variable "custom_tags" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      tag_key = string
      tag_val = string
    }
  ))
  default = []
}

variable "docker_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      app_sync_frequency                 = number
      ca_tls_key_and_certificate_ref     = string
      client_tls_key_and_certificate_ref = string
      container_port_match_http_service  = bool
      coredump_directory                 = string
      disable_auto_backend_service_sync  = bool
      disable_auto_frontend_service_sync = bool
      disable_auto_se_creation           = bool
      docker_registry_se = set(object(
        {
          oshift_registry = set(object(
            {
              registry_namespace = string
              registry_service   = string
              registry_vip = set(object(
                {
                  addr = string
                  type = string
                }
              ))
            }
          ))
          password = string
          private  = bool
          registry = string
          username = string
        }
      ))
      east_west_placement_subnet = set(object(
        {
          ip_addr = set(object(
            {
              addr = string
              type = string
            }
          ))
          mask = number
        }
      ))
      enable_event_subscription         = bool
      feproxy_container_port_as_service = bool
      feproxy_vips_enable_proxy_arp     = bool
      fleet_endpoint                    = string
      http_container_ports              = list(number)
      se_deployment_method              = string
      se_exclude_attributes = list(object(
        {
          attribute = string
          value     = string
        }
      ))
      se_include_attributes = list(object(
        {
          attribute = string
          value     = string
        }
      ))
      se_spawn_rate                      = number
      se_volume                          = string
      services_accessible_all_interfaces = bool
      ssh_user_ref                       = string
      ucp_nodes                          = list(string)
      use_container_ip_port              = bool
      use_controller_image               = bool
    }
  ))
  default = []
}

variable "gcp_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cloud_credentials_ref = string
      encryption_key_id     = string
      firewall_target_tags  = list(string)
      gcs_bucket_name       = string
      gcs_project_id        = string
      network_config = set(object(
        {
          config = string
          inband = set(object(
            {
              vpc_network_name = string
              vpc_project_id   = string
              vpc_subnet_name  = string
            }
          ))
          one_arm = set(object(
            {
              data_vpc_network_name       = string
              data_vpc_project_id         = string
              data_vpc_subnet_name        = string
              management_vpc_network_name = string
              management_vpc_subnet_name  = string
            }
          ))
          two_arm = set(object(
            {
              backend_data_vpc_network_name  = string
              backend_data_vpc_subnet_name   = string
              frontend_data_vpc_network_name = string
              frontend_data_vpc_project_id   = string
              frontend_data_vpc_subnet_name  = string
              management_vpc_network_name    = string
              management_vpc_subnet_name     = string
            }
          ))
        }
      ))
      region_name   = string
      se_project_id = string
      vip_allocation_strategy = set(object(
        {
          ilb = set(object(
            {
              cloud_router_names = list(string)
            }
          ))
          mode = string
          routes = set(object(
            {
              match_se_group_subnet = bool
            }
          ))
        }
      ))
      zones = list(string)
    }
  ))
  default = []
}

variable "linuxserver_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      hosts = list(object(
        {
          host_attr = list(object(
            {
              attr_key = string
              attr_val = string
            }
          ))
          host_ip = set(object(
            {
              addr = string
              type = string
            }
          ))
          node_availability_zone = string
          se_group_ref           = string
        }
      ))
      se_inband_mgmt      = bool
      se_log_disk_path    = string
      se_log_disk_size_gb = number
      se_sys_disk_path    = string
      se_sys_disk_size_gb = number
      ssh_user_ref        = string
    }
  ))
  default = []
}

variable "nsx_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      avi_nsx_prefix       = string
      nsx_manager_name     = string
      nsx_manager_password = string
      nsx_manager_username = string
      nsx_poll_time        = number
    }
  ))
  default = []
}

variable "openstack_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      admin_tenant            = string
      admin_tenant_uuid       = string
      allowed_address_pairs   = bool
      anti_affinity           = bool
      auth_url                = string
      config_drive            = bool
      contrail_disable_policy = bool
      contrail_endpoint       = string
      contrail_plugin         = bool
      custom_se_image_properties = list(object(
        {
          name  = string
          value = string
        }
      ))
      external_networks = bool
      free_floatingips  = bool
      hypervisor        = string
      hypervisor_properties = list(object(
        {
          hypervisor = string
          image_properties = list(object(
            {
              name  = string
              value = string
            }
          ))
        }
      ))
      img_format              = string
      import_keystone_tenants = bool
      insecure                = bool
      keystone_host           = string
      map_admin_to_cloudadmin = bool
      mgmt_network_name       = string
      mgmt_network_uuid       = string
      name_owner              = bool
      neutron_rbac            = bool
      nuage_organization      = string
      nuage_password          = string
      nuage_port              = number
      nuage_username          = string
      nuage_virtualip         = bool
      nuage_vsd_host          = string
      password                = string
      port_security           = bool
      privilege               = string
      prov_name               = list(string)
      provider_vip_networks = list(object(
        {
          os_network_uuid = string
          os_tenant_uuids = list(string)
        }
      ))
      region = string
      role_mapping = list(object(
        {
          avi_role = string
          os_role  = string
        }
      ))
      security_groups        = bool
      tenant_se              = bool
      use_admin_url          = bool
      use_internal_endpoints = bool
      use_keystone_auth      = bool
      use_nuagevip           = bool
      username               = string
    }
  ))
  default = []
}

variable "oshiftk8s_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      app_sync_frequency = number
      auto_assign_fqdn   = bool
      avi_bridge_subnet = set(object(
        {
          ip_addr = set(object(
            {
              addr = string
              type = string
            }
          ))
          mask = number
        }
      ))
      ca_tls_key_and_certificate_ref       = string
      client_tls_key_and_certificate_ref   = string
      cluster_tag                          = string
      container_port_match_http_service    = bool
      coredump_directory                   = string
      default_service_as_east_west_service = bool
      disable_auto_backend_service_sync    = bool
      disable_auto_frontend_service_sync   = bool
      disable_auto_gs_sync                 = bool
      disable_auto_se_creation             = bool
      docker_endpoint                      = string
      docker_registry_se = set(object(
        {
          oshift_registry = set(object(
            {
              registry_namespace = string
              registry_service   = string
              registry_vip = set(object(
                {
                  addr = string
                  type = string
                }
              ))
            }
          ))
          password = string
          private  = bool
          registry = string
          username = string
        }
      ))
      east_west_placement_subnet = set(object(
        {
          ip_addr = set(object(
            {
              addr = string
              type = string
            }
          ))
          mask = number
        }
      ))
      enable_event_subscription      = bool
      enable_route_ingress_hardening = bool
      feproxy_vips_enable_proxy_arp  = bool
      http_container_ports           = list(number)
      ing_exclude_attributes = list(object(
        {
          attribute = string
          value     = string
        }
      ))
      ing_include_attributes = list(object(
        {
          attribute = string
          value     = string
        }
      ))
      l4_health_monitoring         = bool
      master_nodes                 = list(string)
      node_availability_zone_label = string
      ns_exclude_attributes = list(object(
        {
          attribute = string
          value     = string
        }
      ))
      ns_include_attributes = list(object(
        {
          attribute = string
          value     = string
        }
      ))
      num_shards              = number
      override_service_ports  = bool
      persistent_volume_claim = string
      routes = list(object(
        {
          if_name           = string
          network_namespace = string
          nexthop = set(object(
            {
              addr = string
              type = string
            }
          ))
          subnet = set(object(
            {
              ip_addr = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              mask = number
            }
          ))
        }
      ))
      sdn_overlay          = bool
      se_deployment_method = string
      se_exclude_attributes = list(object(
        {
          attribute = string
          value     = string
        }
      ))
      se_image_pull_secret = string
      se_include_attributes = list(object(
        {
          attribute = string
          value     = string
        }
      ))
      se_namespace = string
      se_pod_tolerations = list(object(
        {
          effect             = string
          key                = string
          operator           = string
          toleration_seconds = number
          value              = string
        }
      ))
      se_priority_class                = string
      se_restart_batch_size            = number
      se_restart_force                 = bool
      se_volume                        = string
      secure_egress_mode               = bool
      service_account_token            = string
      shard_prefix                     = string
      shared_virtualservice_namespace  = bool
      ssh_user_ref                     = string
      sync_not_ready_addresses         = bool
      use_controller_image             = bool
      use_resource_definition_as_ssot  = bool
      use_scheduling_disabled_nodes    = bool
      use_service_cluster_ip_as_ew_vip = bool
      vip_default_gateway = set(object(
        {
          addr = string
          type = string
        }
      ))
    }
  ))
  default = []
}

variable "proxy_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      host     = string
      password = string
      port     = number
      username = string
    }
  ))
  default = []
}

variable "rancher_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access_key                         = string
      app_sync_frequency                 = number
      container_port_match_http_service  = bool
      coredump_directory                 = string
      disable_auto_backend_service_sync  = bool
      disable_auto_frontend_service_sync = bool
      disable_auto_se_creation           = bool
      docker_registry_se = set(object(
        {
          oshift_registry = set(object(
            {
              registry_namespace = string
              registry_service   = string
              registry_vip = set(object(
                {
                  addr = string
                  type = string
                }
              ))
            }
          ))
          password = string
          private  = bool
          registry = string
          username = string
        }
      ))
      east_west_placement_subnet = set(object(
        {
          ip_addr = set(object(
            {
              addr = string
              type = string
            }
          ))
          mask = number
        }
      ))
      enable_event_subscription         = bool
      feproxy_container_port_as_service = bool
      feproxy_vips_enable_proxy_arp     = bool
      fleet_endpoint                    = string
      http_container_ports              = list(number)
      nuage_controller = set(object(
        {
          nuage_organization = string
          nuage_password     = string
          nuage_port         = number
          nuage_username     = string
          nuage_vsd_host     = string
          se_domain          = string
          se_enterprise      = string
          se_network         = string
          se_policy_group    = string
          se_user            = string
          se_zone            = string
        }
      ))
      rancher_servers      = list(string)
      se_deployment_method = string
      se_exclude_attributes = list(object(
        {
          attribute = string
          value     = string
        }
      ))
      se_include_attributes = list(object(
        {
          attribute = string
          value     = string
        }
      ))
      se_spawn_rate                      = number
      se_volume                          = string
      secret_key                         = string
      services_accessible_all_interfaces = bool
      ssh_user_ref                       = string
      use_container_ip_port              = bool
      use_controller_image               = bool
    }
  ))
  default = []
}

variable "vca_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      privilege        = string
      vca_host         = string
      vca_instance     = string
      vca_mgmt_network = string
      vca_orgnization  = string
      vca_password     = string
      vca_username     = string
      vca_vdc          = string
    }
  ))
  default = []
}

variable "vcenter_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      datacenter = string
      management_ip_subnet = set(object(
        {
          ip_addr = set(object(
            {
              addr = string
              type = string
            }
          ))
          mask = number
        }
      ))
      management_network           = string
      password                     = string
      privilege                    = string
      username                     = string
      vcenter_template_se_location = string
      vcenter_url                  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_cloud" "this" {
  apic_mode                    = var.apic_mode
  autoscale_polling_interval   = var.autoscale_polling_interval
  dhcp_enabled                 = var.dhcp_enabled
  dns_provider_ref             = var.dns_provider_ref
  dns_resolution_on_se         = var.dns_resolution_on_se
  east_west_dns_provider_ref   = var.east_west_dns_provider_ref
  east_west_ipam_provider_ref  = var.east_west_ipam_provider_ref
  enable_vip_on_all_interfaces = var.enable_vip_on_all_interfaces
  enable_vip_static_routes     = var.enable_vip_static_routes
  ip6_autocfg_enabled          = var.ip6_autocfg_enabled
  ipam_provider_ref            = var.ipam_provider_ref
  license_tier                 = var.license_tier
  license_type                 = var.license_type
  mtu                          = var.mtu
  name                         = var.name
  obj_name_prefix              = var.obj_name_prefix
  prefer_static_routes         = var.prefer_static_routes
  se_group_template_ref        = var.se_group_template_ref
  state_based_dns_registration = var.state_based_dns_registration
  tenant_ref                   = var.tenant_ref
  uuid                         = var.uuid
  vtype                        = var.vtype

  dynamic "apic_configuration" {
    for_each = var.apic_configuration
    content {
      apic_admin_tenant = apic_configuration.value["apic_admin_tenant"]
      apic_domain       = apic_configuration.value["apic_domain"]
      apic_name         = apic_configuration.value["apic_name"]
      apic_password     = apic_configuration.value["apic_password"]
      apic_username     = apic_configuration.value["apic_username"]
      context_aware     = apic_configuration.value["context_aware"]
      se_tunnel_mode    = apic_configuration.value["se_tunnel_mode"]
    }
  }

  dynamic "aws_configuration" {
    for_each = var.aws_configuration
    content {
      access_key_id              = aws_configuration.value["access_key_id"]
      asg_poll_interval          = aws_configuration.value["asg_poll_interval"]
      free_elasticips            = aws_configuration.value["free_elasticips"]
      iam_assume_role            = aws_configuration.value["iam_assume_role"]
      publish_vip_to_public_zone = aws_configuration.value["publish_vip_to_public_zone"]
      region                     = aws_configuration.value["region"]
      route53_integration        = aws_configuration.value["route53_integration"]
      secret_access_key          = aws_configuration.value["secret_access_key"]
      ttl                        = aws_configuration.value["ttl"]
      use_iam_roles              = aws_configuration.value["use_iam_roles"]
      use_sns_sqs                = aws_configuration.value["use_sns_sqs"]
      vpc                        = aws_configuration.value["vpc"]
      vpc_id                     = aws_configuration.value["vpc_id"]

      dynamic "ebs_encryption" {
        for_each = aws_configuration.value.ebs_encryption
        content {
          master_key = ebs_encryption.value["master_key"]
          mode       = ebs_encryption.value["mode"]
        }
      }

      dynamic "s3_encryption" {
        for_each = aws_configuration.value.s3_encryption
        content {
          master_key = s3_encryption.value["master_key"]
          mode       = s3_encryption.value["mode"]
        }
      }

      dynamic "sqs_encryption" {
        for_each = aws_configuration.value.sqs_encryption
        content {
          master_key = sqs_encryption.value["master_key"]
          mode       = sqs_encryption.value["mode"]
        }
      }

      dynamic "zones" {
        for_each = aws_configuration.value.zones
        content {
          availability_zone = zones.value["availability_zone"]
          mgmt_network_name = zones.value["mgmt_network_name"]
          mgmt_network_uuid = zones.value["mgmt_network_uuid"]
        }
      }

    }
  }

  dynamic "azure_configuration" {
    for_each = var.azure_configuration
    content {
      availability_zones    = azure_configuration.value["availability_zones"]
      cloud_credentials_ref = azure_configuration.value["cloud_credentials_ref"]
      location              = azure_configuration.value["location"]
      resource_group        = azure_configuration.value["resource_group"]
      subscription_id       = azure_configuration.value["subscription_id"]
      use_azure_dns         = azure_configuration.value["use_azure_dns"]
      use_enhanced_ha       = azure_configuration.value["use_enhanced_ha"]
      use_managed_disks     = azure_configuration.value["use_managed_disks"]
      use_standard_alb      = azure_configuration.value["use_standard_alb"]

      dynamic "network_info" {
        for_each = azure_configuration.value.network_info
        content {
          management_network_id = network_info.value["management_network_id"]
          se_network_id         = network_info.value["se_network_id"]
          virtual_network_id    = network_info.value["virtual_network_id"]
        }
      }

    }
  }

  dynamic "cloudstack_configuration" {
    for_each = var.cloudstack_configuration
    content {
      access_key_id     = cloudstack_configuration.value["access_key_id"]
      api_url           = cloudstack_configuration.value["api_url"]
      cntr_public_ip    = cloudstack_configuration.value["cntr_public_ip"]
      hypervisor        = cloudstack_configuration.value["hypervisor"]
      mgmt_network_name = cloudstack_configuration.value["mgmt_network_name"]
      mgmt_network_uuid = cloudstack_configuration.value["mgmt_network_uuid"]
      secret_access_key = cloudstack_configuration.value["secret_access_key"]
    }
  }

  dynamic "custom_tags" {
    for_each = var.custom_tags
    content {
      tag_key = custom_tags.value["tag_key"]
      tag_val = custom_tags.value["tag_val"]
    }
  }

  dynamic "docker_configuration" {
    for_each = var.docker_configuration
    content {
      app_sync_frequency                 = docker_configuration.value["app_sync_frequency"]
      ca_tls_key_and_certificate_ref     = docker_configuration.value["ca_tls_key_and_certificate_ref"]
      client_tls_key_and_certificate_ref = docker_configuration.value["client_tls_key_and_certificate_ref"]
      container_port_match_http_service  = docker_configuration.value["container_port_match_http_service"]
      coredump_directory                 = docker_configuration.value["coredump_directory"]
      disable_auto_backend_service_sync  = docker_configuration.value["disable_auto_backend_service_sync"]
      disable_auto_frontend_service_sync = docker_configuration.value["disable_auto_frontend_service_sync"]
      disable_auto_se_creation           = docker_configuration.value["disable_auto_se_creation"]
      enable_event_subscription          = docker_configuration.value["enable_event_subscription"]
      feproxy_container_port_as_service  = docker_configuration.value["feproxy_container_port_as_service"]
      feproxy_vips_enable_proxy_arp      = docker_configuration.value["feproxy_vips_enable_proxy_arp"]
      fleet_endpoint                     = docker_configuration.value["fleet_endpoint"]
      http_container_ports               = docker_configuration.value["http_container_ports"]
      se_deployment_method               = docker_configuration.value["se_deployment_method"]
      se_spawn_rate                      = docker_configuration.value["se_spawn_rate"]
      se_volume                          = docker_configuration.value["se_volume"]
      services_accessible_all_interfaces = docker_configuration.value["services_accessible_all_interfaces"]
      ssh_user_ref                       = docker_configuration.value["ssh_user_ref"]
      ucp_nodes                          = docker_configuration.value["ucp_nodes"]
      use_container_ip_port              = docker_configuration.value["use_container_ip_port"]
      use_controller_image               = docker_configuration.value["use_controller_image"]

      dynamic "docker_registry_se" {
        for_each = docker_configuration.value.docker_registry_se
        content {
          password = docker_registry_se.value["password"]
          private  = docker_registry_se.value["private"]
          registry = docker_registry_se.value["registry"]
          username = docker_registry_se.value["username"]

          dynamic "oshift_registry" {
            for_each = docker_registry_se.value.oshift_registry
            content {
              registry_namespace = oshift_registry.value["registry_namespace"]
              registry_service   = oshift_registry.value["registry_service"]

              dynamic "registry_vip" {
                for_each = oshift_registry.value.registry_vip
                content {
                  addr = registry_vip.value["addr"]
                  type = registry_vip.value["type"]
                }
              }

            }
          }

        }
      }

      dynamic "east_west_placement_subnet" {
        for_each = docker_configuration.value.east_west_placement_subnet
        content {
          mask = east_west_placement_subnet.value["mask"]

          dynamic "ip_addr" {
            for_each = east_west_placement_subnet.value.ip_addr
            content {
              addr = ip_addr.value["addr"]
              type = ip_addr.value["type"]
            }
          }

        }
      }

      dynamic "se_exclude_attributes" {
        for_each = docker_configuration.value.se_exclude_attributes
        content {
          attribute = se_exclude_attributes.value["attribute"]
          value     = se_exclude_attributes.value["value"]
        }
      }

      dynamic "se_include_attributes" {
        for_each = docker_configuration.value.se_include_attributes
        content {
          attribute = se_include_attributes.value["attribute"]
          value     = se_include_attributes.value["value"]
        }
      }

    }
  }

  dynamic "gcp_configuration" {
    for_each = var.gcp_configuration
    content {
      cloud_credentials_ref = gcp_configuration.value["cloud_credentials_ref"]
      encryption_key_id     = gcp_configuration.value["encryption_key_id"]
      firewall_target_tags  = gcp_configuration.value["firewall_target_tags"]
      gcs_bucket_name       = gcp_configuration.value["gcs_bucket_name"]
      gcs_project_id        = gcp_configuration.value["gcs_project_id"]
      region_name           = gcp_configuration.value["region_name"]
      se_project_id         = gcp_configuration.value["se_project_id"]
      zones                 = gcp_configuration.value["zones"]

      dynamic "network_config" {
        for_each = gcp_configuration.value.network_config
        content {
          config = network_config.value["config"]

          dynamic "inband" {
            for_each = network_config.value.inband
            content {
              vpc_network_name = inband.value["vpc_network_name"]
              vpc_project_id   = inband.value["vpc_project_id"]
              vpc_subnet_name  = inband.value["vpc_subnet_name"]
            }
          }

          dynamic "one_arm" {
            for_each = network_config.value.one_arm
            content {
              data_vpc_network_name       = one_arm.value["data_vpc_network_name"]
              data_vpc_project_id         = one_arm.value["data_vpc_project_id"]
              data_vpc_subnet_name        = one_arm.value["data_vpc_subnet_name"]
              management_vpc_network_name = one_arm.value["management_vpc_network_name"]
              management_vpc_subnet_name  = one_arm.value["management_vpc_subnet_name"]
            }
          }

          dynamic "two_arm" {
            for_each = network_config.value.two_arm
            content {
              backend_data_vpc_network_name  = two_arm.value["backend_data_vpc_network_name"]
              backend_data_vpc_subnet_name   = two_arm.value["backend_data_vpc_subnet_name"]
              frontend_data_vpc_network_name = two_arm.value["frontend_data_vpc_network_name"]
              frontend_data_vpc_project_id   = two_arm.value["frontend_data_vpc_project_id"]
              frontend_data_vpc_subnet_name  = two_arm.value["frontend_data_vpc_subnet_name"]
              management_vpc_network_name    = two_arm.value["management_vpc_network_name"]
              management_vpc_subnet_name     = two_arm.value["management_vpc_subnet_name"]
            }
          }

        }
      }

      dynamic "vip_allocation_strategy" {
        for_each = gcp_configuration.value.vip_allocation_strategy
        content {
          mode = vip_allocation_strategy.value["mode"]

          dynamic "ilb" {
            for_each = vip_allocation_strategy.value.ilb
            content {
              cloud_router_names = ilb.value["cloud_router_names"]
            }
          }

          dynamic "routes" {
            for_each = vip_allocation_strategy.value.routes
            content {
              match_se_group_subnet = routes.value["match_se_group_subnet"]
            }
          }

        }
      }

    }
  }

  dynamic "linuxserver_configuration" {
    for_each = var.linuxserver_configuration
    content {
      se_inband_mgmt      = linuxserver_configuration.value["se_inband_mgmt"]
      se_log_disk_path    = linuxserver_configuration.value["se_log_disk_path"]
      se_log_disk_size_gb = linuxserver_configuration.value["se_log_disk_size_gb"]
      se_sys_disk_path    = linuxserver_configuration.value["se_sys_disk_path"]
      se_sys_disk_size_gb = linuxserver_configuration.value["se_sys_disk_size_gb"]
      ssh_user_ref        = linuxserver_configuration.value["ssh_user_ref"]

      dynamic "hosts" {
        for_each = linuxserver_configuration.value.hosts
        content {
          node_availability_zone = hosts.value["node_availability_zone"]
          se_group_ref           = hosts.value["se_group_ref"]

          dynamic "host_attr" {
            for_each = hosts.value.host_attr
            content {
              attr_key = host_attr.value["attr_key"]
              attr_val = host_attr.value["attr_val"]
            }
          }

          dynamic "host_ip" {
            for_each = hosts.value.host_ip
            content {
              addr = host_ip.value["addr"]
              type = host_ip.value["type"]
            }
          }

        }
      }

    }
  }

  dynamic "nsx_configuration" {
    for_each = var.nsx_configuration
    content {
      avi_nsx_prefix       = nsx_configuration.value["avi_nsx_prefix"]
      nsx_manager_name     = nsx_configuration.value["nsx_manager_name"]
      nsx_manager_password = nsx_configuration.value["nsx_manager_password"]
      nsx_manager_username = nsx_configuration.value["nsx_manager_username"]
      nsx_poll_time        = nsx_configuration.value["nsx_poll_time"]
    }
  }

  dynamic "openstack_configuration" {
    for_each = var.openstack_configuration
    content {
      admin_tenant            = openstack_configuration.value["admin_tenant"]
      admin_tenant_uuid       = openstack_configuration.value["admin_tenant_uuid"]
      allowed_address_pairs   = openstack_configuration.value["allowed_address_pairs"]
      anti_affinity           = openstack_configuration.value["anti_affinity"]
      auth_url                = openstack_configuration.value["auth_url"]
      config_drive            = openstack_configuration.value["config_drive"]
      contrail_disable_policy = openstack_configuration.value["contrail_disable_policy"]
      contrail_endpoint       = openstack_configuration.value["contrail_endpoint"]
      contrail_plugin         = openstack_configuration.value["contrail_plugin"]
      external_networks       = openstack_configuration.value["external_networks"]
      free_floatingips        = openstack_configuration.value["free_floatingips"]
      hypervisor              = openstack_configuration.value["hypervisor"]
      img_format              = openstack_configuration.value["img_format"]
      import_keystone_tenants = openstack_configuration.value["import_keystone_tenants"]
      insecure                = openstack_configuration.value["insecure"]
      keystone_host           = openstack_configuration.value["keystone_host"]
      map_admin_to_cloudadmin = openstack_configuration.value["map_admin_to_cloudadmin"]
      mgmt_network_name       = openstack_configuration.value["mgmt_network_name"]
      mgmt_network_uuid       = openstack_configuration.value["mgmt_network_uuid"]
      name_owner              = openstack_configuration.value["name_owner"]
      neutron_rbac            = openstack_configuration.value["neutron_rbac"]
      nuage_organization      = openstack_configuration.value["nuage_organization"]
      nuage_password          = openstack_configuration.value["nuage_password"]
      nuage_port              = openstack_configuration.value["nuage_port"]
      nuage_username          = openstack_configuration.value["nuage_username"]
      nuage_virtualip         = openstack_configuration.value["nuage_virtualip"]
      nuage_vsd_host          = openstack_configuration.value["nuage_vsd_host"]
      password                = openstack_configuration.value["password"]
      port_security           = openstack_configuration.value["port_security"]
      privilege               = openstack_configuration.value["privilege"]
      prov_name               = openstack_configuration.value["prov_name"]
      region                  = openstack_configuration.value["region"]
      security_groups         = openstack_configuration.value["security_groups"]
      tenant_se               = openstack_configuration.value["tenant_se"]
      use_admin_url           = openstack_configuration.value["use_admin_url"]
      use_internal_endpoints  = openstack_configuration.value["use_internal_endpoints"]
      use_keystone_auth       = openstack_configuration.value["use_keystone_auth"]
      use_nuagevip            = openstack_configuration.value["use_nuagevip"]
      username                = openstack_configuration.value["username"]

      dynamic "custom_se_image_properties" {
        for_each = openstack_configuration.value.custom_se_image_properties
        content {
          name  = custom_se_image_properties.value["name"]
          value = custom_se_image_properties.value["value"]
        }
      }

      dynamic "hypervisor_properties" {
        for_each = openstack_configuration.value.hypervisor_properties
        content {
          hypervisor = hypervisor_properties.value["hypervisor"]

          dynamic "image_properties" {
            for_each = hypervisor_properties.value.image_properties
            content {
              name  = image_properties.value["name"]
              value = image_properties.value["value"]
            }
          }

        }
      }

      dynamic "provider_vip_networks" {
        for_each = openstack_configuration.value.provider_vip_networks
        content {
          os_network_uuid = provider_vip_networks.value["os_network_uuid"]
          os_tenant_uuids = provider_vip_networks.value["os_tenant_uuids"]
        }
      }

      dynamic "role_mapping" {
        for_each = openstack_configuration.value.role_mapping
        content {
          avi_role = role_mapping.value["avi_role"]
          os_role  = role_mapping.value["os_role"]
        }
      }

    }
  }

  dynamic "oshiftk8s_configuration" {
    for_each = var.oshiftk8s_configuration
    content {
      app_sync_frequency                   = oshiftk8s_configuration.value["app_sync_frequency"]
      auto_assign_fqdn                     = oshiftk8s_configuration.value["auto_assign_fqdn"]
      ca_tls_key_and_certificate_ref       = oshiftk8s_configuration.value["ca_tls_key_and_certificate_ref"]
      client_tls_key_and_certificate_ref   = oshiftk8s_configuration.value["client_tls_key_and_certificate_ref"]
      cluster_tag                          = oshiftk8s_configuration.value["cluster_tag"]
      container_port_match_http_service    = oshiftk8s_configuration.value["container_port_match_http_service"]
      coredump_directory                   = oshiftk8s_configuration.value["coredump_directory"]
      default_service_as_east_west_service = oshiftk8s_configuration.value["default_service_as_east_west_service"]
      disable_auto_backend_service_sync    = oshiftk8s_configuration.value["disable_auto_backend_service_sync"]
      disable_auto_frontend_service_sync   = oshiftk8s_configuration.value["disable_auto_frontend_service_sync"]
      disable_auto_gs_sync                 = oshiftk8s_configuration.value["disable_auto_gs_sync"]
      disable_auto_se_creation             = oshiftk8s_configuration.value["disable_auto_se_creation"]
      docker_endpoint                      = oshiftk8s_configuration.value["docker_endpoint"]
      enable_event_subscription            = oshiftk8s_configuration.value["enable_event_subscription"]
      enable_route_ingress_hardening       = oshiftk8s_configuration.value["enable_route_ingress_hardening"]
      feproxy_vips_enable_proxy_arp        = oshiftk8s_configuration.value["feproxy_vips_enable_proxy_arp"]
      http_container_ports                 = oshiftk8s_configuration.value["http_container_ports"]
      l4_health_monitoring                 = oshiftk8s_configuration.value["l4_health_monitoring"]
      master_nodes                         = oshiftk8s_configuration.value["master_nodes"]
      node_availability_zone_label         = oshiftk8s_configuration.value["node_availability_zone_label"]
      num_shards                           = oshiftk8s_configuration.value["num_shards"]
      override_service_ports               = oshiftk8s_configuration.value["override_service_ports"]
      persistent_volume_claim              = oshiftk8s_configuration.value["persistent_volume_claim"]
      sdn_overlay                          = oshiftk8s_configuration.value["sdn_overlay"]
      se_deployment_method                 = oshiftk8s_configuration.value["se_deployment_method"]
      se_image_pull_secret                 = oshiftk8s_configuration.value["se_image_pull_secret"]
      se_namespace                         = oshiftk8s_configuration.value["se_namespace"]
      se_priority_class                    = oshiftk8s_configuration.value["se_priority_class"]
      se_restart_batch_size                = oshiftk8s_configuration.value["se_restart_batch_size"]
      se_restart_force                     = oshiftk8s_configuration.value["se_restart_force"]
      se_volume                            = oshiftk8s_configuration.value["se_volume"]
      secure_egress_mode                   = oshiftk8s_configuration.value["secure_egress_mode"]
      service_account_token                = oshiftk8s_configuration.value["service_account_token"]
      shard_prefix                         = oshiftk8s_configuration.value["shard_prefix"]
      shared_virtualservice_namespace      = oshiftk8s_configuration.value["shared_virtualservice_namespace"]
      ssh_user_ref                         = oshiftk8s_configuration.value["ssh_user_ref"]
      sync_not_ready_addresses             = oshiftk8s_configuration.value["sync_not_ready_addresses"]
      use_controller_image                 = oshiftk8s_configuration.value["use_controller_image"]
      use_resource_definition_as_ssot      = oshiftk8s_configuration.value["use_resource_definition_as_ssot"]
      use_scheduling_disabled_nodes        = oshiftk8s_configuration.value["use_scheduling_disabled_nodes"]
      use_service_cluster_ip_as_ew_vip     = oshiftk8s_configuration.value["use_service_cluster_ip_as_ew_vip"]

      dynamic "avi_bridge_subnet" {
        for_each = oshiftk8s_configuration.value.avi_bridge_subnet
        content {
          mask = avi_bridge_subnet.value["mask"]

          dynamic "ip_addr" {
            for_each = avi_bridge_subnet.value.ip_addr
            content {
              addr = ip_addr.value["addr"]
              type = ip_addr.value["type"]
            }
          }

        }
      }

      dynamic "docker_registry_se" {
        for_each = oshiftk8s_configuration.value.docker_registry_se
        content {
          password = docker_registry_se.value["password"]
          private  = docker_registry_se.value["private"]
          registry = docker_registry_se.value["registry"]
          username = docker_registry_se.value["username"]

          dynamic "oshift_registry" {
            for_each = docker_registry_se.value.oshift_registry
            content {
              registry_namespace = oshift_registry.value["registry_namespace"]
              registry_service   = oshift_registry.value["registry_service"]

              dynamic "registry_vip" {
                for_each = oshift_registry.value.registry_vip
                content {
                  addr = registry_vip.value["addr"]
                  type = registry_vip.value["type"]
                }
              }

            }
          }

        }
      }

      dynamic "east_west_placement_subnet" {
        for_each = oshiftk8s_configuration.value.east_west_placement_subnet
        content {
          mask = east_west_placement_subnet.value["mask"]

          dynamic "ip_addr" {
            for_each = east_west_placement_subnet.value.ip_addr
            content {
              addr = ip_addr.value["addr"]
              type = ip_addr.value["type"]
            }
          }

        }
      }

      dynamic "ing_exclude_attributes" {
        for_each = oshiftk8s_configuration.value.ing_exclude_attributes
        content {
          attribute = ing_exclude_attributes.value["attribute"]
          value     = ing_exclude_attributes.value["value"]
        }
      }

      dynamic "ing_include_attributes" {
        for_each = oshiftk8s_configuration.value.ing_include_attributes
        content {
          attribute = ing_include_attributes.value["attribute"]
          value     = ing_include_attributes.value["value"]
        }
      }

      dynamic "ns_exclude_attributes" {
        for_each = oshiftk8s_configuration.value.ns_exclude_attributes
        content {
          attribute = ns_exclude_attributes.value["attribute"]
          value     = ns_exclude_attributes.value["value"]
        }
      }

      dynamic "ns_include_attributes" {
        for_each = oshiftk8s_configuration.value.ns_include_attributes
        content {
          attribute = ns_include_attributes.value["attribute"]
          value     = ns_include_attributes.value["value"]
        }
      }

      dynamic "routes" {
        for_each = oshiftk8s_configuration.value.routes
        content {
          if_name           = routes.value["if_name"]
          network_namespace = routes.value["network_namespace"]

          dynamic "nexthop" {
            for_each = routes.value.nexthop
            content {
              addr = nexthop.value["addr"]
              type = nexthop.value["type"]
            }
          }

          dynamic "subnet" {
            for_each = routes.value.subnet
            content {
              mask = subnet.value["mask"]

              dynamic "ip_addr" {
                for_each = subnet.value.ip_addr
                content {
                  addr = ip_addr.value["addr"]
                  type = ip_addr.value["type"]
                }
              }

            }
          }

        }
      }

      dynamic "se_exclude_attributes" {
        for_each = oshiftk8s_configuration.value.se_exclude_attributes
        content {
          attribute = se_exclude_attributes.value["attribute"]
          value     = se_exclude_attributes.value["value"]
        }
      }

      dynamic "se_include_attributes" {
        for_each = oshiftk8s_configuration.value.se_include_attributes
        content {
          attribute = se_include_attributes.value["attribute"]
          value     = se_include_attributes.value["value"]
        }
      }

      dynamic "se_pod_tolerations" {
        for_each = oshiftk8s_configuration.value.se_pod_tolerations
        content {
          effect             = se_pod_tolerations.value["effect"]
          key                = se_pod_tolerations.value["key"]
          operator           = se_pod_tolerations.value["operator"]
          toleration_seconds = se_pod_tolerations.value["toleration_seconds"]
          value              = se_pod_tolerations.value["value"]
        }
      }

      dynamic "vip_default_gateway" {
        for_each = oshiftk8s_configuration.value.vip_default_gateway
        content {
          addr = vip_default_gateway.value["addr"]
          type = vip_default_gateway.value["type"]
        }
      }

    }
  }

  dynamic "proxy_configuration" {
    for_each = var.proxy_configuration
    content {
      host     = proxy_configuration.value["host"]
      password = proxy_configuration.value["password"]
      port     = proxy_configuration.value["port"]
      username = proxy_configuration.value["username"]
    }
  }

  dynamic "rancher_configuration" {
    for_each = var.rancher_configuration
    content {
      access_key                         = rancher_configuration.value["access_key"]
      app_sync_frequency                 = rancher_configuration.value["app_sync_frequency"]
      container_port_match_http_service  = rancher_configuration.value["container_port_match_http_service"]
      coredump_directory                 = rancher_configuration.value["coredump_directory"]
      disable_auto_backend_service_sync  = rancher_configuration.value["disable_auto_backend_service_sync"]
      disable_auto_frontend_service_sync = rancher_configuration.value["disable_auto_frontend_service_sync"]
      disable_auto_se_creation           = rancher_configuration.value["disable_auto_se_creation"]
      enable_event_subscription          = rancher_configuration.value["enable_event_subscription"]
      feproxy_container_port_as_service  = rancher_configuration.value["feproxy_container_port_as_service"]
      feproxy_vips_enable_proxy_arp      = rancher_configuration.value["feproxy_vips_enable_proxy_arp"]
      fleet_endpoint                     = rancher_configuration.value["fleet_endpoint"]
      http_container_ports               = rancher_configuration.value["http_container_ports"]
      rancher_servers                    = rancher_configuration.value["rancher_servers"]
      se_deployment_method               = rancher_configuration.value["se_deployment_method"]
      se_spawn_rate                      = rancher_configuration.value["se_spawn_rate"]
      se_volume                          = rancher_configuration.value["se_volume"]
      secret_key                         = rancher_configuration.value["secret_key"]
      services_accessible_all_interfaces = rancher_configuration.value["services_accessible_all_interfaces"]
      ssh_user_ref                       = rancher_configuration.value["ssh_user_ref"]
      use_container_ip_port              = rancher_configuration.value["use_container_ip_port"]
      use_controller_image               = rancher_configuration.value["use_controller_image"]

      dynamic "docker_registry_se" {
        for_each = rancher_configuration.value.docker_registry_se
        content {
          password = docker_registry_se.value["password"]
          private  = docker_registry_se.value["private"]
          registry = docker_registry_se.value["registry"]
          username = docker_registry_se.value["username"]

          dynamic "oshift_registry" {
            for_each = docker_registry_se.value.oshift_registry
            content {
              registry_namespace = oshift_registry.value["registry_namespace"]
              registry_service   = oshift_registry.value["registry_service"]

              dynamic "registry_vip" {
                for_each = oshift_registry.value.registry_vip
                content {
                  addr = registry_vip.value["addr"]
                  type = registry_vip.value["type"]
                }
              }

            }
          }

        }
      }

      dynamic "east_west_placement_subnet" {
        for_each = rancher_configuration.value.east_west_placement_subnet
        content {
          mask = east_west_placement_subnet.value["mask"]

          dynamic "ip_addr" {
            for_each = east_west_placement_subnet.value.ip_addr
            content {
              addr = ip_addr.value["addr"]
              type = ip_addr.value["type"]
            }
          }

        }
      }

      dynamic "nuage_controller" {
        for_each = rancher_configuration.value.nuage_controller
        content {
          nuage_organization = nuage_controller.value["nuage_organization"]
          nuage_password     = nuage_controller.value["nuage_password"]
          nuage_port         = nuage_controller.value["nuage_port"]
          nuage_username     = nuage_controller.value["nuage_username"]
          nuage_vsd_host     = nuage_controller.value["nuage_vsd_host"]
          se_domain          = nuage_controller.value["se_domain"]
          se_enterprise      = nuage_controller.value["se_enterprise"]
          se_network         = nuage_controller.value["se_network"]
          se_policy_group    = nuage_controller.value["se_policy_group"]
          se_user            = nuage_controller.value["se_user"]
          se_zone            = nuage_controller.value["se_zone"]
        }
      }

      dynamic "se_exclude_attributes" {
        for_each = rancher_configuration.value.se_exclude_attributes
        content {
          attribute = se_exclude_attributes.value["attribute"]
          value     = se_exclude_attributes.value["value"]
        }
      }

      dynamic "se_include_attributes" {
        for_each = rancher_configuration.value.se_include_attributes
        content {
          attribute = se_include_attributes.value["attribute"]
          value     = se_include_attributes.value["value"]
        }
      }

    }
  }

  dynamic "vca_configuration" {
    for_each = var.vca_configuration
    content {
      privilege        = vca_configuration.value["privilege"]
      vca_host         = vca_configuration.value["vca_host"]
      vca_instance     = vca_configuration.value["vca_instance"]
      vca_mgmt_network = vca_configuration.value["vca_mgmt_network"]
      vca_orgnization  = vca_configuration.value["vca_orgnization"]
      vca_password     = vca_configuration.value["vca_password"]
      vca_username     = vca_configuration.value["vca_username"]
      vca_vdc          = vca_configuration.value["vca_vdc"]
    }
  }

  dynamic "vcenter_configuration" {
    for_each = var.vcenter_configuration
    content {
      datacenter                   = vcenter_configuration.value["datacenter"]
      management_network           = vcenter_configuration.value["management_network"]
      password                     = vcenter_configuration.value["password"]
      privilege                    = vcenter_configuration.value["privilege"]
      username                     = vcenter_configuration.value["username"]
      vcenter_template_se_location = vcenter_configuration.value["vcenter_template_se_location"]
      vcenter_url                  = vcenter_configuration.value["vcenter_url"]

      dynamic "management_ip_subnet" {
        for_each = vcenter_configuration.value.management_ip_subnet
        content {
          mask = management_ip_subnet.value["mask"]

          dynamic "ip_addr" {
            for_each = management_ip_subnet.value.ip_addr
            content {
              addr = ip_addr.value["addr"]
              type = ip_addr.value["type"]
            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "dns_provider_ref" {
  description = "returns a string"
  value       = avi_cloud.this.dns_provider_ref
}

output "east_west_dns_provider_ref" {
  description = "returns a string"
  value       = avi_cloud.this.east_west_dns_provider_ref
}

output "east_west_ipam_provider_ref" {
  description = "returns a string"
  value       = avi_cloud.this.east_west_ipam_provider_ref
}

output "id" {
  description = "returns a string"
  value       = avi_cloud.this.id
}

output "ipam_provider_ref" {
  description = "returns a string"
  value       = avi_cloud.this.ipam_provider_ref
}

output "license_tier" {
  description = "returns a string"
  value       = avi_cloud.this.license_tier
}

output "license_type" {
  description = "returns a string"
  value       = avi_cloud.this.license_type
}

output "obj_name_prefix" {
  description = "returns a string"
  value       = avi_cloud.this.obj_name_prefix
}

output "se_group_template_ref" {
  description = "returns a string"
  value       = avi_cloud.this.se_group_template_ref
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_cloud.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_cloud.this.uuid
}

output "this" {
  value = avi_cloud.this
}
```

[top](#index)