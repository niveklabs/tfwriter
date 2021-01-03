# alicloud_resource_manager_handshakes

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_resource_manager_handshakes" {
  source = "./modules/alicloud/d/alicloud_resource_manager_handshakes"

  # ids - (optional) is a type of list of string
  ids = []
  # output_file - (optional) is a type of string
  output_file = null
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

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_resource_manager_handshakes" "this" {
  ids         = var.ids
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "handshakes" {
  description = "returns a list of object"
  value       = data.alicloud_resource_manager_handshakes.this.handshakes
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_resource_manager_handshakes.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_resource_manager_handshakes.this.ids
}

output "this" {
  value = alicloud_resource_manager_handshakes.this
}
```

[top](#index)