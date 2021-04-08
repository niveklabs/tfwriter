# vmc_sddc

[back](../vmc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vmc = ">= 1.5.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vmc_sddc" {
  source = "./modules/vmc/r/vmc_sddc"

  # delay_account_link - (optional) is a type of bool
  delay_account_link = null
  # deployment_type - (optional) is a type of string
  deployment_type = null
  # edrs_policy_type - (optional) is a type of string
  edrs_policy_type = null
  # enable_edrs - (optional) is a type of bool
  enable_edrs = null
  # host_instance_type - (optional) is a type of string
  host_instance_type = null
  # intranet_mtu_uplink - (optional) is a type of number
  intranet_mtu_uplink = null
  # max_hosts - (optional) is a type of number
  max_hosts = null
  # min_hosts - (optional) is a type of number
  min_hosts = null
  # num_host - (required) is a type of number
  num_host = null
  # provider_type - (optional) is a type of string
  provider_type = null
  # region - (required) is a type of string
  region = null
  # sddc_name - (required) is a type of string
  sddc_name = null
  # sddc_template_id - (optional) is a type of string
  sddc_template_id = null
  # sddc_type - (optional) is a type of string
  sddc_type = null
  # size - (optional) is a type of string
  size = null
  # skip_creating_vxlan - (optional) is a type of bool
  skip_creating_vxlan = null
  # sso_domain - (optional) is a type of string
  sso_domain = null
  # storage_capacity - (optional) is a type of string
  storage_capacity = null
  # vpc_cidr - (optional) is a type of string
  vpc_cidr = null
  # vxlan_subnet - (optional) is a type of string
  vxlan_subnet = null

  account_link_sddc_config = [{
    connected_account_id = null
    customer_subnet_ids  = []
  }]

  microsoft_licensing_config = [{
    mssql_licensing   = null
    windows_licensing = null
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
variable "delay_account_link" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "deployment_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "edrs_policy_type" {
  description = "(optional) - The EDRS policy type. This can either be 'cost', 'performance', 'storage-scaleup' or 'rapid-scaleup'. Default : storage-scaleup. "
  type        = string
  default     = null
}

variable "enable_edrs" {
  description = "(optional) - True if EDRS is enabled"
  type        = bool
  default     = null
}

variable "host_instance_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "intranet_mtu_uplink" {
  description = "(optional) - Uplink MTU of direct connect, SDDC-grouping and outposts traffic in edge tier-0 router port."
  type        = number
  default     = null
}

variable "max_hosts" {
  description = "(optional) - The maximum number of hosts that the cluster can scale out to."
  type        = number
  default     = null
}

variable "min_hosts" {
  description = "(optional) - The minimum number of hosts that the cluster can scale in to."
  type        = number
  default     = null
}

variable "num_host" {
  description = "(required)"
  type        = number
}

variable "provider_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(required)"
  type        = string
}

variable "sddc_name" {
  description = "(required)"
  type        = string
}

variable "sddc_template_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sddc_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "size" {
  description = "(optional) - The size of the vCenter and NSX appliances. 'large' or 'LARGE' SDDC size corresponds to a large vCenter appliance and large NSX appliance. 'medium' or 'MEDIUM' SDDC size corresponds to medium vCenter appliance and medium NSX appliance. Default : 'medium'."
  type        = string
  default     = null
}

variable "skip_creating_vxlan" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "sso_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_capacity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_cidr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vxlan_subnet" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "account_link_sddc_config" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      connected_account_id = string
      customer_subnet_ids  = list(string)
    }
  ))
  default = []
}

variable "microsoft_licensing_config" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      mssql_licensing   = string
      windows_licensing = string
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
resource "vmc_sddc" "this" {
  # delay_account_link - (optional) is a type of bool
  delay_account_link = var.delay_account_link
  # deployment_type - (optional) is a type of string
  deployment_type = var.deployment_type
  # edrs_policy_type - (optional) is a type of string
  edrs_policy_type = var.edrs_policy_type
  # enable_edrs - (optional) is a type of bool
  enable_edrs = var.enable_edrs
  # host_instance_type - (optional) is a type of string
  host_instance_type = var.host_instance_type
  # intranet_mtu_uplink - (optional) is a type of number
  intranet_mtu_uplink = var.intranet_mtu_uplink
  # max_hosts - (optional) is a type of number
  max_hosts = var.max_hosts
  # min_hosts - (optional) is a type of number
  min_hosts = var.min_hosts
  # num_host - (required) is a type of number
  num_host = var.num_host
  # provider_type - (optional) is a type of string
  provider_type = var.provider_type
  # region - (required) is a type of string
  region = var.region
  # sddc_name - (required) is a type of string
  sddc_name = var.sddc_name
  # sddc_template_id - (optional) is a type of string
  sddc_template_id = var.sddc_template_id
  # sddc_type - (optional) is a type of string
  sddc_type = var.sddc_type
  # size - (optional) is a type of string
  size = var.size
  # skip_creating_vxlan - (optional) is a type of bool
  skip_creating_vxlan = var.skip_creating_vxlan
  # sso_domain - (optional) is a type of string
  sso_domain = var.sso_domain
  # storage_capacity - (optional) is a type of string
  storage_capacity = var.storage_capacity
  # vpc_cidr - (optional) is a type of string
  vpc_cidr = var.vpc_cidr
  # vxlan_subnet - (optional) is a type of string
  vxlan_subnet = var.vxlan_subnet

  dynamic "account_link_sddc_config" {
    for_each = var.account_link_sddc_config
    content {
      # connected_account_id - (optional) is a type of string
      connected_account_id = account_link_sddc_config.value["connected_account_id"]
      # customer_subnet_ids - (optional) is a type of list of string
      customer_subnet_ids = account_link_sddc_config.value["customer_subnet_ids"]
    }
  }

  dynamic "microsoft_licensing_config" {
    for_each = var.microsoft_licensing_config
    content {
      # mssql_licensing - (optional) is a type of string
      mssql_licensing = microsoft_licensing_config.value["mssql_licensing"]
      # windows_licensing - (optional) is a type of string
      windows_licensing = microsoft_licensing_config.value["windows_licensing"]
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
output "availability_zones" {
  description = "returns a list of string"
  value       = vmc_sddc.this.availability_zones
}

output "cloud_password" {
  description = "returns a string"
  value       = vmc_sddc.this.cloud_password
}

output "cloud_username" {
  description = "returns a string"
  value       = vmc_sddc.this.cloud_username
}

output "cluster_id" {
  description = "returns a string"
  value       = vmc_sddc.this.cluster_id
}

output "cluster_info" {
  description = "returns a map of string"
  value       = vmc_sddc.this.cluster_info
}

output "id" {
  description = "returns a string"
  value       = vmc_sddc.this.id
}

output "nsxt_reverse_proxy_url" {
  description = "returns a string"
  value       = vmc_sddc.this.nsxt_reverse_proxy_url
}

output "sddc_size" {
  description = "returns a map of string"
  value       = vmc_sddc.this.sddc_size
}

output "sddc_state" {
  description = "returns a string"
  value       = vmc_sddc.this.sddc_state
}

output "vc_url" {
  description = "returns a string"
  value       = vmc_sddc.this.vc_url
}

output "this" {
  value = vmc_sddc.this
}
```

[top](#index)