# alicloud_privatelink_vpc_endpoint_service_resources

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
module "alicloud_privatelink_vpc_endpoint_service_resources" {
  source = "./modules/alicloud/d/alicloud_privatelink_vpc_endpoint_service_resources"

  # output_file - (optional) is a type of string
  output_file = null
  # service_id - (required) is a type of string
  service_id = null
}
```

[top](#index)

### Variables

```terraform
variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_privatelink_vpc_endpoint_service_resources" "this" {
  output_file = var.output_file
  service_id  = var.service_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_privatelink_vpc_endpoint_service_resources.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_privatelink_vpc_endpoint_service_resources.this.ids
}

output "resources" {
  description = "returns a list of object"
  value       = data.alicloud_privatelink_vpc_endpoint_service_resources.this.resources
}

output "this" {
  value = alicloud_privatelink_vpc_endpoint_service_resources.this
}
```

[top](#index)