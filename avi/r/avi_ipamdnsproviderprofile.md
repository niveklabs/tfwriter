# avi_ipamdnsproviderprofile

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
module "avi_ipamdnsproviderprofile" {
  source = "./modules/avi/r/avi_ipamdnsproviderprofile"

  # allocate_ip_in_vrf - (optional) is a type of bool
  allocate_ip_in_vrf = null
  # name - (required) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # type - (required) is a type of string
  type = null
  # uuid - (optional) is a type of string
  uuid = null

  aws_profile = [{
    access_key_id              = null
    egress_service_subnets     = []
    iam_assume_role            = null
    publish_vip_to_public_zone = null
    region                     = null
    secret_access_key          = null
    ttl                        = null
    usable_domains             = []
    usable_network_uuids       = []
    use_iam_roles              = null
    vpc                        = null
    vpc_id                     = null
    zones = [{
      availability_zone    = null
      usable_network_uuids = []
    }]
  }]

  azure_profile = [{
    azure_serviceprincipal = [{
      application_id       = null
      authentication_token = null
      tenant_id            = null
    }]
    azure_userpass = [{
      password    = null
      tenant_name = null
      username    = null
    }]
    egress_service_subnets = []
    resource_group         = null
    subscription_id        = null
    usable_domains         = []
    usable_network_uuids   = []
    use_enhanced_ha        = null
    use_standard_alb       = null
    virtual_network_ids    = []
  }]

  custom_profile = [{
    custom_ipam_dns_profile_ref = null
    dynamic_params = [{
      is_dynamic   = null
      is_sensitive = null
      name         = null
      value        = null
    }]
    usable_domains = []
    usable_subnets = [{
      ip_addr = [{
        addr = null
        type = null
      }]
      mask = null
    }]
  }]

  gcp_profile = [{
    match_se_group_subnet   = null
    network_host_project_id = null
    region_name             = null
    se_project_id           = null
    usable_network_refs     = []
    use_gcp_network         = null
    vpc_network_name        = null
  }]

  infoblox_profile = [{
    dns_view = null
    extensible_attributes = [{
      is_dynamic   = null
      is_sensitive = null
      name         = null
      value        = null
    }]
    ip_address = [{
      addr = null
      type = null
    }]
    network_view = null
    password     = null
    usable_alloc_subnets = [{
      subnet = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
      subnet6 = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
    }]
    usable_domains = []
    username       = null
    wapi_version   = null
  }]

  internal_profile = [{
    dns_service_domain = [{
      domain_name  = null
      num_dns_ip   = null
      pass_through = null
      record_ttl   = null
    }]
    dns_virtualservice_ref = null
    ttl                    = null
    usable_network_refs    = []
  }]

  oci_profile = [{
    cloud_credentials_ref = null
    region                = null
    tenancy               = null
    vcn_compartment_id    = null
    vcn_id                = null
  }]

  openstack_profile = [{
    keystone_host    = null
    password         = null
    region           = null
    tenant           = null
    username         = null
    vip_network_name = null
  }]

  proxy_configuration = [{
    host     = null
    password = null
    port     = null
    username = null
  }]

  tencent_profile = [{
    cloud_credentials_ref = null
    region                = null
    usable_subnet_ids     = []
    vpc_id                = null
    zones = [{
      availability_zone = null
      usable_subnet_id  = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allocate_ip_in_vrf" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "aws_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access_key_id              = string
      egress_service_subnets     = list(string)
      iam_assume_role            = string
      publish_vip_to_public_zone = bool
      region                     = string
      secret_access_key          = string
      ttl                        = number
      usable_domains             = list(string)
      usable_network_uuids       = list(string)
      use_iam_roles              = bool
      vpc                        = string
      vpc_id                     = string
      zones = list(object(
        {
          availability_zone    = string
          usable_network_uuids = list(string)
        }
      ))
    }
  ))
  default = []
}

variable "azure_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      azure_serviceprincipal = set(object(
        {
          application_id       = string
          authentication_token = string
          tenant_id            = string
        }
      ))
      azure_userpass = set(object(
        {
          password    = string
          tenant_name = string
          username    = string
        }
      ))
      egress_service_subnets = list(string)
      resource_group         = string
      subscription_id        = string
      usable_domains         = list(string)
      usable_network_uuids   = list(string)
      use_enhanced_ha        = bool
      use_standard_alb       = bool
      virtual_network_ids    = list(string)
    }
  ))
  default = []
}

variable "custom_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      custom_ipam_dns_profile_ref = string
      dynamic_params = list(object(
        {
          is_dynamic   = bool
          is_sensitive = bool
          name         = string
          value        = string
        }
      ))
      usable_domains = list(string)
      usable_subnets = list(object(
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
  default = []
}

variable "gcp_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      match_se_group_subnet   = bool
      network_host_project_id = string
      region_name             = string
      se_project_id           = string
      usable_network_refs     = list(string)
      use_gcp_network         = bool
      vpc_network_name        = string
    }
  ))
  default = []
}

variable "infoblox_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      dns_view = string
      extensible_attributes = list(object(
        {
          is_dynamic   = bool
          is_sensitive = bool
          name         = string
          value        = string
        }
      ))
      ip_address = set(object(
        {
          addr = string
          type = string
        }
      ))
      network_view = string
      password     = string
      usable_alloc_subnets = list(object(
        {
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
          subnet6 = set(object(
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
      usable_domains = list(string)
      username       = string
      wapi_version   = string
    }
  ))
  default = []
}

variable "internal_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      dns_service_domain = list(object(
        {
          domain_name  = string
          num_dns_ip   = number
          pass_through = bool
          record_ttl   = number
        }
      ))
      dns_virtualservice_ref = string
      ttl                    = number
      usable_network_refs    = list(string)
    }
  ))
  default = []
}

variable "oci_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cloud_credentials_ref = string
      region                = string
      tenancy               = string
      vcn_compartment_id    = string
      vcn_id                = string
    }
  ))
  default = []
}

variable "openstack_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      keystone_host    = string
      password         = string
      region           = string
      tenant           = string
      username         = string
      vip_network_name = string
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

variable "tencent_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cloud_credentials_ref = string
      region                = string
      usable_subnet_ids     = list(string)
      vpc_id                = string
      zones = list(object(
        {
          availability_zone = string
          usable_subnet_id  = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_ipamdnsproviderprofile" "this" {
  # allocate_ip_in_vrf - (optional) is a type of bool
  allocate_ip_in_vrf = var.allocate_ip_in_vrf
  # name - (required) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # type - (required) is a type of string
  type = var.type
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "aws_profile" {
    for_each = var.aws_profile
    content {
      # access_key_id - (optional) is a type of string
      access_key_id = aws_profile.value["access_key_id"]
      # egress_service_subnets - (optional) is a type of list of string
      egress_service_subnets = aws_profile.value["egress_service_subnets"]
      # iam_assume_role - (optional) is a type of string
      iam_assume_role = aws_profile.value["iam_assume_role"]
      # publish_vip_to_public_zone - (optional) is a type of bool
      publish_vip_to_public_zone = aws_profile.value["publish_vip_to_public_zone"]
      # region - (optional) is a type of string
      region = aws_profile.value["region"]
      # secret_access_key - (optional) is a type of string
      secret_access_key = aws_profile.value["secret_access_key"]
      # ttl - (optional) is a type of number
      ttl = aws_profile.value["ttl"]
      # usable_domains - (optional) is a type of list of string
      usable_domains = aws_profile.value["usable_domains"]
      # usable_network_uuids - (optional) is a type of list of string
      usable_network_uuids = aws_profile.value["usable_network_uuids"]
      # use_iam_roles - (optional) is a type of bool
      use_iam_roles = aws_profile.value["use_iam_roles"]
      # vpc - (optional) is a type of string
      vpc = aws_profile.value["vpc"]
      # vpc_id - (required) is a type of string
      vpc_id = aws_profile.value["vpc_id"]

      dynamic "zones" {
        for_each = aws_profile.value.zones
        content {
          # availability_zone - (required) is a type of string
          availability_zone = zones.value["availability_zone"]
          # usable_network_uuids - (optional) is a type of list of string
          usable_network_uuids = zones.value["usable_network_uuids"]
        }
      }

    }
  }

  dynamic "azure_profile" {
    for_each = var.azure_profile
    content {
      # egress_service_subnets - (optional) is a type of list of string
      egress_service_subnets = azure_profile.value["egress_service_subnets"]
      # resource_group - (optional) is a type of string
      resource_group = azure_profile.value["resource_group"]
      # subscription_id - (optional) is a type of string
      subscription_id = azure_profile.value["subscription_id"]
      # usable_domains - (optional) is a type of list of string
      usable_domains = azure_profile.value["usable_domains"]
      # usable_network_uuids - (optional) is a type of list of string
      usable_network_uuids = azure_profile.value["usable_network_uuids"]
      # use_enhanced_ha - (optional) is a type of bool
      use_enhanced_ha = azure_profile.value["use_enhanced_ha"]
      # use_standard_alb - (optional) is a type of bool
      use_standard_alb = azure_profile.value["use_standard_alb"]
      # virtual_network_ids - (optional) is a type of list of string
      virtual_network_ids = azure_profile.value["virtual_network_ids"]

      dynamic "azure_serviceprincipal" {
        for_each = azure_profile.value.azure_serviceprincipal
        content {
          # application_id - (optional) is a type of string
          application_id = azure_serviceprincipal.value["application_id"]
          # authentication_token - (optional) is a type of string
          authentication_token = azure_serviceprincipal.value["authentication_token"]
          # tenant_id - (optional) is a type of string
          tenant_id = azure_serviceprincipal.value["tenant_id"]
        }
      }

      dynamic "azure_userpass" {
        for_each = azure_profile.value.azure_userpass
        content {
          # password - (optional) is a type of string
          password = azure_userpass.value["password"]
          # tenant_name - (optional) is a type of string
          tenant_name = azure_userpass.value["tenant_name"]
          # username - (optional) is a type of string
          username = azure_userpass.value["username"]
        }
      }

    }
  }

  dynamic "custom_profile" {
    for_each = var.custom_profile
    content {
      # custom_ipam_dns_profile_ref - (optional) is a type of string
      custom_ipam_dns_profile_ref = custom_profile.value["custom_ipam_dns_profile_ref"]
      # usable_domains - (optional) is a type of list of string
      usable_domains = custom_profile.value["usable_domains"]

      dynamic "dynamic_params" {
        for_each = custom_profile.value.dynamic_params
        content {
          # is_dynamic - (optional) is a type of bool
          is_dynamic = dynamic_params.value["is_dynamic"]
          # is_sensitive - (optional) is a type of bool
          is_sensitive = dynamic_params.value["is_sensitive"]
          # name - (required) is a type of string
          name = dynamic_params.value["name"]
          # value - (optional) is a type of string
          value = dynamic_params.value["value"]
        }
      }

      dynamic "usable_subnets" {
        for_each = custom_profile.value.usable_subnets
        content {
          # mask - (required) is a type of number
          mask = usable_subnets.value["mask"]

          dynamic "ip_addr" {
            for_each = usable_subnets.value.ip_addr
            content {
              # addr - (required) is a type of string
              addr = ip_addr.value["addr"]
              # type - (required) is a type of string
              type = ip_addr.value["type"]
            }
          }

        }
      }

    }
  }

  dynamic "gcp_profile" {
    for_each = var.gcp_profile
    content {
      # match_se_group_subnet - (optional) is a type of bool
      match_se_group_subnet = gcp_profile.value["match_se_group_subnet"]
      # network_host_project_id - (optional) is a type of string
      network_host_project_id = gcp_profile.value["network_host_project_id"]
      # region_name - (optional) is a type of string
      region_name = gcp_profile.value["region_name"]
      # se_project_id - (optional) is a type of string
      se_project_id = gcp_profile.value["se_project_id"]
      # usable_network_refs - (optional) is a type of list of string
      usable_network_refs = gcp_profile.value["usable_network_refs"]
      # use_gcp_network - (optional) is a type of bool
      use_gcp_network = gcp_profile.value["use_gcp_network"]
      # vpc_network_name - (optional) is a type of string
      vpc_network_name = gcp_profile.value["vpc_network_name"]
    }
  }

  dynamic "infoblox_profile" {
    for_each = var.infoblox_profile
    content {
      # dns_view - (optional) is a type of string
      dns_view = infoblox_profile.value["dns_view"]
      # network_view - (optional) is a type of string
      network_view = infoblox_profile.value["network_view"]
      # password - (required) is a type of string
      password = infoblox_profile.value["password"]
      # usable_domains - (optional) is a type of list of string
      usable_domains = infoblox_profile.value["usable_domains"]
      # username - (required) is a type of string
      username = infoblox_profile.value["username"]
      # wapi_version - (optional) is a type of string
      wapi_version = infoblox_profile.value["wapi_version"]

      dynamic "extensible_attributes" {
        for_each = infoblox_profile.value.extensible_attributes
        content {
          # is_dynamic - (optional) is a type of bool
          is_dynamic = extensible_attributes.value["is_dynamic"]
          # is_sensitive - (optional) is a type of bool
          is_sensitive = extensible_attributes.value["is_sensitive"]
          # name - (required) is a type of string
          name = extensible_attributes.value["name"]
          # value - (optional) is a type of string
          value = extensible_attributes.value["value"]
        }
      }

      dynamic "ip_address" {
        for_each = infoblox_profile.value.ip_address
        content {
          # addr - (required) is a type of string
          addr = ip_address.value["addr"]
          # type - (required) is a type of string
          type = ip_address.value["type"]
        }
      }

      dynamic "usable_alloc_subnets" {
        for_each = infoblox_profile.value.usable_alloc_subnets
        content {

          dynamic "subnet" {
            for_each = usable_alloc_subnets.value.subnet
            content {
              # mask - (required) is a type of number
              mask = subnet.value["mask"]

              dynamic "ip_addr" {
                for_each = subnet.value.ip_addr
                content {
                  # addr - (required) is a type of string
                  addr = ip_addr.value["addr"]
                  # type - (required) is a type of string
                  type = ip_addr.value["type"]
                }
              }

            }
          }

          dynamic "subnet6" {
            for_each = usable_alloc_subnets.value.subnet6
            content {
              # mask - (required) is a type of number
              mask = subnet6.value["mask"]

              dynamic "ip_addr" {
                for_each = subnet6.value.ip_addr
                content {
                  # addr - (required) is a type of string
                  addr = ip_addr.value["addr"]
                  # type - (required) is a type of string
                  type = ip_addr.value["type"]
                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "internal_profile" {
    for_each = var.internal_profile
    content {
      # dns_virtualservice_ref - (optional) is a type of string
      dns_virtualservice_ref = internal_profile.value["dns_virtualservice_ref"]
      # ttl - (optional) is a type of number
      ttl = internal_profile.value["ttl"]
      # usable_network_refs - (optional) is a type of list of string
      usable_network_refs = internal_profile.value["usable_network_refs"]

      dynamic "dns_service_domain" {
        for_each = internal_profile.value.dns_service_domain
        content {
          # domain_name - (required) is a type of string
          domain_name = dns_service_domain.value["domain_name"]
          # num_dns_ip - (optional) is a type of number
          num_dns_ip = dns_service_domain.value["num_dns_ip"]
          # pass_through - (optional) is a type of bool
          pass_through = dns_service_domain.value["pass_through"]
          # record_ttl - (optional) is a type of number
          record_ttl = dns_service_domain.value["record_ttl"]
        }
      }

    }
  }

  dynamic "oci_profile" {
    for_each = var.oci_profile
    content {
      # cloud_credentials_ref - (optional) is a type of string
      cloud_credentials_ref = oci_profile.value["cloud_credentials_ref"]
      # region - (optional) is a type of string
      region = oci_profile.value["region"]
      # tenancy - (optional) is a type of string
      tenancy = oci_profile.value["tenancy"]
      # vcn_compartment_id - (optional) is a type of string
      vcn_compartment_id = oci_profile.value["vcn_compartment_id"]
      # vcn_id - (optional) is a type of string
      vcn_id = oci_profile.value["vcn_id"]
    }
  }

  dynamic "openstack_profile" {
    for_each = var.openstack_profile
    content {
      # keystone_host - (optional) is a type of string
      keystone_host = openstack_profile.value["keystone_host"]
      # password - (optional) is a type of string
      password = openstack_profile.value["password"]
      # region - (optional) is a type of string
      region = openstack_profile.value["region"]
      # tenant - (optional) is a type of string
      tenant = openstack_profile.value["tenant"]
      # username - (optional) is a type of string
      username = openstack_profile.value["username"]
      # vip_network_name - (optional) is a type of string
      vip_network_name = openstack_profile.value["vip_network_name"]
    }
  }

  dynamic "proxy_configuration" {
    for_each = var.proxy_configuration
    content {
      # host - (required) is a type of string
      host = proxy_configuration.value["host"]
      # password - (optional) is a type of string
      password = proxy_configuration.value["password"]
      # port - (required) is a type of number
      port = proxy_configuration.value["port"]
      # username - (optional) is a type of string
      username = proxy_configuration.value["username"]
    }
  }

  dynamic "tencent_profile" {
    for_each = var.tencent_profile
    content {
      # cloud_credentials_ref - (optional) is a type of string
      cloud_credentials_ref = tencent_profile.value["cloud_credentials_ref"]
      # region - (optional) is a type of string
      region = tencent_profile.value["region"]
      # usable_subnet_ids - (optional) is a type of list of string
      usable_subnet_ids = tencent_profile.value["usable_subnet_ids"]
      # vpc_id - (optional) is a type of string
      vpc_id = tencent_profile.value["vpc_id"]

      dynamic "zones" {
        for_each = tencent_profile.value.zones
        content {
          # availability_zone - (optional) is a type of string
          availability_zone = zones.value["availability_zone"]
          # usable_subnet_id - (optional) is a type of string
          usable_subnet_id = zones.value["usable_subnet_id"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = avi_ipamdnsproviderprofile.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_ipamdnsproviderprofile.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_ipamdnsproviderprofile.this.uuid
}

output "this" {
  value = avi_ipamdnsproviderprofile.this
}
```

[top](#index)