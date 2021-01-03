# alicloud_kvstore_connections

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
module "alicloud_kvstore_connections" {
  source = "./modules/alicloud/d/alicloud_kvstore_connections"

  # ids - (required) is a type of list of string
  ids = []
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "ids" {
  description = "(required)"
  type        = list(string)
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
data "alicloud_kvstore_connections" "this" {
  ids         = var.ids
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "connections" {
  description = "returns a list of object"
  value       = data.alicloud_kvstore_connections.this.connections
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_kvstore_connections.this.id
}

output "this" {
  value = alicloud_kvstore_connections.this
}
```

[top](#index)