# fortios_system_sdnconnector

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_sdnconnector" {
  source = "./modules/fortios/r/fortios_system_sdnconnector"

  # access_key - (optional) is a type of string
  access_key = null
  # api_key - (optional) is a type of string
  api_key = null
  # azure_region - (optional) is a type of string
  azure_region = null
  # client_id - (optional) is a type of string
  client_id = null
  # client_secret - (optional) is a type of string
  client_secret = null
  # compartment_id - (optional) is a type of string
  compartment_id = null
  # compute_generation - (optional) is a type of number
  compute_generation = null
  # domain - (optional) is a type of string
  domain = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # gcp_project - (optional) is a type of string
  gcp_project = null
  # group_name - (optional) is a type of string
  group_name = null
  # ha_status - (optional) is a type of string
  ha_status = null
  # ibm_region - (optional) is a type of string
  ibm_region = null
  # key_passwd - (optional) is a type of string
  key_passwd = null
  # login_endpoint - (optional) is a type of string
  login_endpoint = null
  # name - (optional) is a type of string
  name = null
  # oci_cert - (optional) is a type of string
  oci_cert = null
  # oci_fingerprint - (optional) is a type of string
  oci_fingerprint = null
  # oci_region - (optional) is a type of string
  oci_region = null
  # oci_region_type - (optional) is a type of string
  oci_region_type = null
  # password - (optional) is a type of string
  password = null
  # private_key - (optional) is a type of string
  private_key = null
  # region - (optional) is a type of string
  region = null
  # resource_group - (optional) is a type of string
  resource_group = null
  # resource_url - (optional) is a type of string
  resource_url = null
  # secret_key - (optional) is a type of string
  secret_key = null
  # secret_token - (optional) is a type of string
  secret_token = null
  # server - (optional) is a type of string
  server = null
  # server_port - (optional) is a type of number
  server_port = null
  # service_account - (optional) is a type of string
  service_account = null
  # status - (required) is a type of string
  status = null
  # subscription_id - (optional) is a type of string
  subscription_id = null
  # tenant_id - (optional) is a type of string
  tenant_id = null
  # type - (required) is a type of string
  type = null
  # update_interval - (optional) is a type of number
  update_interval = null
  # use_metadata_iam - (optional) is a type of string
  use_metadata_iam = null
  # user_id - (optional) is a type of string
  user_id = null
  # username - (optional) is a type of string
  username = null
  # vcenter_password - (optional) is a type of string
  vcenter_password = null
  # vcenter_server - (optional) is a type of string
  vcenter_server = null
  # vcenter_username - (optional) is a type of string
  vcenter_username = null
  # vpc_id - (optional) is a type of string
  vpc_id = null

  external_ip = [{
    name = null
  }]

  nic = [{
    ip = [{
      name           = null
      public_ip      = null
      resource_group = null
    }]
    name = null
  }]

  route = [{
    name = null
  }]

  route_table = [{
    name           = null
    resource_group = null
    route = [{
      name     = null
      next_hop = null
    }]
    subscription_id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "access_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "api_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "azure_region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "client_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "client_secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compute_generation" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gcp_project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ha_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ibm_region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_passwd" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "login_endpoint" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "oci_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "oci_fingerprint" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "oci_region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "oci_region_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secret_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secret_token" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "service_account" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(required)"
  type        = string
}

variable "subscription_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "update_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "use_metadata_iam" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vcenter_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vcenter_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vcenter_username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "external_ip" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "nic" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip = list(object(
        {
          name           = string
          public_ip      = string
          resource_group = string
        }
      ))
      name = string
    }
  ))
  default = []
}

variable "route" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "route_table" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name           = string
      resource_group = string
      route = list(object(
        {
          name     = string
          next_hop = string
        }
      ))
      subscription_id = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_sdnconnector" "this" {
  # access_key - (optional) is a type of string
  access_key = var.access_key
  # api_key - (optional) is a type of string
  api_key = var.api_key
  # azure_region - (optional) is a type of string
  azure_region = var.azure_region
  # client_id - (optional) is a type of string
  client_id = var.client_id
  # client_secret - (optional) is a type of string
  client_secret = var.client_secret
  # compartment_id - (optional) is a type of string
  compartment_id = var.compartment_id
  # compute_generation - (optional) is a type of number
  compute_generation = var.compute_generation
  # domain - (optional) is a type of string
  domain = var.domain
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # gcp_project - (optional) is a type of string
  gcp_project = var.gcp_project
  # group_name - (optional) is a type of string
  group_name = var.group_name
  # ha_status - (optional) is a type of string
  ha_status = var.ha_status
  # ibm_region - (optional) is a type of string
  ibm_region = var.ibm_region
  # key_passwd - (optional) is a type of string
  key_passwd = var.key_passwd
  # login_endpoint - (optional) is a type of string
  login_endpoint = var.login_endpoint
  # name - (optional) is a type of string
  name = var.name
  # oci_cert - (optional) is a type of string
  oci_cert = var.oci_cert
  # oci_fingerprint - (optional) is a type of string
  oci_fingerprint = var.oci_fingerprint
  # oci_region - (optional) is a type of string
  oci_region = var.oci_region
  # oci_region_type - (optional) is a type of string
  oci_region_type = var.oci_region_type
  # password - (optional) is a type of string
  password = var.password
  # private_key - (optional) is a type of string
  private_key = var.private_key
  # region - (optional) is a type of string
  region = var.region
  # resource_group - (optional) is a type of string
  resource_group = var.resource_group
  # resource_url - (optional) is a type of string
  resource_url = var.resource_url
  # secret_key - (optional) is a type of string
  secret_key = var.secret_key
  # secret_token - (optional) is a type of string
  secret_token = var.secret_token
  # server - (optional) is a type of string
  server = var.server
  # server_port - (optional) is a type of number
  server_port = var.server_port
  # service_account - (optional) is a type of string
  service_account = var.service_account
  # status - (required) is a type of string
  status = var.status
  # subscription_id - (optional) is a type of string
  subscription_id = var.subscription_id
  # tenant_id - (optional) is a type of string
  tenant_id = var.tenant_id
  # type - (required) is a type of string
  type = var.type
  # update_interval - (optional) is a type of number
  update_interval = var.update_interval
  # use_metadata_iam - (optional) is a type of string
  use_metadata_iam = var.use_metadata_iam
  # user_id - (optional) is a type of string
  user_id = var.user_id
  # username - (optional) is a type of string
  username = var.username
  # vcenter_password - (optional) is a type of string
  vcenter_password = var.vcenter_password
  # vcenter_server - (optional) is a type of string
  vcenter_server = var.vcenter_server
  # vcenter_username - (optional) is a type of string
  vcenter_username = var.vcenter_username
  # vpc_id - (optional) is a type of string
  vpc_id = var.vpc_id

  dynamic "external_ip" {
    for_each = var.external_ip
    content {
      # name - (optional) is a type of string
      name = external_ip.value["name"]
    }
  }

  dynamic "nic" {
    for_each = var.nic
    content {
      # name - (optional) is a type of string
      name = nic.value["name"]

      dynamic "ip" {
        for_each = nic.value.ip
        content {
          # name - (optional) is a type of string
          name = ip.value["name"]
          # public_ip - (optional) is a type of string
          public_ip = ip.value["public_ip"]
          # resource_group - (optional) is a type of string
          resource_group = ip.value["resource_group"]
        }
      }

    }
  }

  dynamic "route" {
    for_each = var.route
    content {
      # name - (optional) is a type of string
      name = route.value["name"]
    }
  }

  dynamic "route_table" {
    for_each = var.route_table
    content {
      # name - (optional) is a type of string
      name = route_table.value["name"]
      # resource_group - (optional) is a type of string
      resource_group = route_table.value["resource_group"]
      # subscription_id - (optional) is a type of string
      subscription_id = route_table.value["subscription_id"]

      dynamic "route" {
        for_each = route_table.value.route
        content {
          # name - (optional) is a type of string
          name = route.value["name"]
          # next_hop - (optional) is a type of string
          next_hop = route.value["next_hop"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "access_key" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.access_key
  sensitive   = true
}

output "azure_region" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.azure_region
}

output "client_id" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.client_id
}

output "compartment_id" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.compartment_id
}

output "compute_generation" {
  description = "returns a number"
  value       = fortios_system_sdnconnector.this.compute_generation
}

output "domain" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.domain
}

output "gcp_project" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.gcp_project
}

output "group_name" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.group_name
}

output "ha_status" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.ha_status
}

output "ibm_region" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.ibm_region
}

output "id" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.id
}

output "login_endpoint" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.login_endpoint
}

output "name" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.name
}

output "oci_cert" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.oci_cert
}

output "oci_fingerprint" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.oci_fingerprint
}

output "oci_region" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.oci_region
}

output "oci_region_type" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.oci_region_type
}

output "password" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.password
  sensitive   = true
}

output "private_key" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.private_key
  sensitive   = true
}

output "region" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.region
}

output "resource_group" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.resource_group
}

output "resource_url" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.resource_url
}

output "secret_token" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.secret_token
  sensitive   = true
}

output "server" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.server
}

output "server_port" {
  description = "returns a number"
  value       = fortios_system_sdnconnector.this.server_port
}

output "service_account" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.service_account
}

output "subscription_id" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.subscription_id
}

output "tenant_id" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.tenant_id
}

output "update_interval" {
  description = "returns a number"
  value       = fortios_system_sdnconnector.this.update_interval
}

output "use_metadata_iam" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.use_metadata_iam
}

output "user_id" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.user_id
}

output "username" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.username
}

output "vcenter_server" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.vcenter_server
}

output "vcenter_username" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.vcenter_username
}

output "vpc_id" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.vpc_id
}

output "this" {
  value = fortios_system_sdnconnector.this
}
```

[top](#index)