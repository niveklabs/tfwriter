# alicloud_cs_serverless_kubernetes

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_cs_serverless_kubernetes" {
  source = "./modules/alicloud/r/alicloud_cs_serverless_kubernetes"

  # client_cert - (optional) is a type of string
  client_cert = null
  # client_key - (optional) is a type of string
  client_key = null
  # cluster_ca_cert - (optional) is a type of string
  cluster_ca_cert = null
  # deletion_protection - (optional) is a type of bool
  deletion_protection = null
  # endpoint_public_access_enabled - (optional) is a type of bool
  endpoint_public_access_enabled = null
  # force_update - (optional) is a type of bool
  force_update = null
  # kube_config - (optional) is a type of string
  kube_config = null
  # load_balancer_spec - (optional) is a type of string
  load_balancer_spec = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # new_nat_gateway - (optional) is a type of bool
  new_nat_gateway = null
  # private_zone - (optional) is a type of bool
  private_zone = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # security_group_id - (optional) is a type of string
  security_group_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # version - (optional) is a type of string
  version = null
  # vpc_id - (required) is a type of string
  vpc_id = null
  # vswitch_id - (optional) is a type of string
  vswitch_id = null
  # vswitch_ids - (optional) is a type of list of string
  vswitch_ids = []

  addons = [{
    config   = null
    disabled = null
    name     = null
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "client_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "client_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_ca_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deletion_protection" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "endpoint_public_access_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "force_update" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "kube_config" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "load_balancer_spec" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "new_nat_gateway" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "private_zone" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(required)"
  type        = string
}

variable "vswitch_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vswitch_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "addons" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      config   = string
      disabled = bool
      name     = string
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cs_serverless_kubernetes" "this" {
  client_cert                    = var.client_cert
  client_key                     = var.client_key
  cluster_ca_cert                = var.cluster_ca_cert
  deletion_protection            = var.deletion_protection
  endpoint_public_access_enabled = var.endpoint_public_access_enabled
  force_update                   = var.force_update
  kube_config                    = var.kube_config
  load_balancer_spec             = var.load_balancer_spec
  name                           = var.name
  name_prefix                    = var.name_prefix
  new_nat_gateway                = var.new_nat_gateway
  private_zone                   = var.private_zone
  resource_group_id              = var.resource_group_id
  security_group_id              = var.security_group_id
  tags                           = var.tags
  version                        = var.version
  vpc_id                         = var.vpc_id
  vswitch_id                     = var.vswitch_id
  vswitch_ids                    = var.vswitch_ids

  dynamic "addons" {
    for_each = var.addons
    content {
      config   = addons.value["config"]
      disabled = addons.value["disabled"]
      name     = addons.value["name"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
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
  value       = alicloud_cs_serverless_kubernetes.this.id
}

output "name" {
  description = "returns a string"
  value       = alicloud_cs_serverless_kubernetes.this.name
}

output "resource_group_id" {
  description = "returns a string"
  value       = alicloud_cs_serverless_kubernetes.this.resource_group_id
}

output "security_group_id" {
  description = "returns a string"
  value       = alicloud_cs_serverless_kubernetes.this.security_group_id
}

output "version" {
  description = "returns a string"
  value       = alicloud_cs_serverless_kubernetes.this.version
}

output "vswitch_ids" {
  description = "returns a list of string"
  value       = alicloud_cs_serverless_kubernetes.this.vswitch_ids
}

output "this" {
  value = alicloud_cs_serverless_kubernetes.this
}
```

[top](#index)