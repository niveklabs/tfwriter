# alicloud_alidns_instances

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_alidns_instances" {
  source = "./modules/alicloud/d/alicloud_alidns_instances"

  # ids - (optional) is a type of list of string
  ids = []
  # lang - (optional) is a type of string
  lang = null
  # output_file - (optional) is a type of string
  output_file = null
  # user_client_ip - (optional) is a type of string
  user_client_ip = null
}
```

[top](#index)

### Variables

```terraform
variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "lang" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_client_ip" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_alidns_instances" "this" {
  ids            = var.ids
  lang           = var.lang
  output_file    = var.output_file
  user_client_ip = var.user_client_ip
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_alidns_instances.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_alidns_instances.this.ids
}

output "instances" {
  description = "returns a list of object"
  value       = data.alicloud_alidns_instances.this.instances
}

output "this" {
  value = alicloud_alidns_instances.this
}
```

[top](#index)