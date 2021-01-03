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
    fortios = ">= 1.6.18"
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
  # azure_region - (optional) is a type of string
  azure_region = null
  # client_id - (optional) is a type of string
  client_id = null
  # client_secret - (optional) is a type of string
  client_secret = null
  # compartment_id - (optional) is a type of string
  compartment_id = null
  # gcp_project - (optional) is a type of string
  gcp_project = null
  # ha_status - (optional) is a type of string
  ha_status = null
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
  # vpc_id - (optional) is a type of string
  vpc_id = null

  external_ip = [{
    name = null
  }]

  nic = [{
    ip = [{
      name      = null
      public_ip = null
    }]
    name = null
  }]

  route = [{
    name = null
  }]

  route_table = [{
    name = null
    route = [{
      name     = null
      next_hop = null
    }]
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

variable "gcp_project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ha_status" {
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
          name      = string
          public_ip = string
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
      name = string
      route = list(object(
        {
          name     = string
          next_hop = string
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
resource "fortios_system_sdnconnector" "this" {
  access_key       = var.access_key
  azure_region     = var.azure_region
  client_id        = var.client_id
  client_secret    = var.client_secret
  compartment_id   = var.compartment_id
  gcp_project      = var.gcp_project
  ha_status        = var.ha_status
  key_passwd       = var.key_passwd
  login_endpoint   = var.login_endpoint
  name             = var.name
  oci_cert         = var.oci_cert
  oci_fingerprint  = var.oci_fingerprint
  oci_region       = var.oci_region
  password         = var.password
  private_key      = var.private_key
  region           = var.region
  resource_group   = var.resource_group
  resource_url     = var.resource_url
  secret_key       = var.secret_key
  secret_token     = var.secret_token
  server           = var.server
  server_port      = var.server_port
  service_account  = var.service_account
  status           = var.status
  subscription_id  = var.subscription_id
  tenant_id        = var.tenant_id
  type             = var.type
  update_interval  = var.update_interval
  use_metadata_iam = var.use_metadata_iam
  user_id          = var.user_id
  username         = var.username
  vpc_id           = var.vpc_id

  dynamic "external_ip" {
    for_each = var.external_ip
    content {
      name = external_ip.value["name"]
    }
  }

  dynamic "nic" {
    for_each = var.nic
    content {
      name = nic.value["name"]

      dynamic "ip" {
        for_each = nic.value.ip
        content {
          name      = ip.value["name"]
          public_ip = ip.value["public_ip"]
        }
      }

    }
  }

  dynamic "route" {
    for_each = var.route
    content {
      name = route.value["name"]
    }
  }

  dynamic "route_table" {
    for_each = var.route_table
    content {
      name = route_table.value["name"]

      dynamic "route" {
        for_each = route_table.value.route
        content {
          name     = route.value["name"]
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

output "gcp_project" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.gcp_project
}

output "ha_status" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.ha_status
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

output "vpc_id" {
  description = "returns a string"
  value       = fortios_system_sdnconnector.this.vpc_id
}

output "this" {
  value = fortios_system_sdnconnector.this
}
```

[top](#index)