# tencentcloud_reserved_instance

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_reserved_instance" {
  source = "./modules/tencentcloud/r/tencentcloud_reserved_instance"

  # config_id - (required) is a type of string
  config_id = null
  # instance_count - (required) is a type of number
  instance_count = null
}
```

[top](#index)

### Variables

```terraform
variable "config_id" {
  description = "(required) - Configuration ID of the reserved instance."
  type        = string
}

variable "instance_count" {
  description = "(required) - Number of reserved instances to be purchased."
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_reserved_instance" "this" {
  # config_id - (required) is a type of string
  config_id = var.config_id
  # instance_count - (required) is a type of number
  instance_count = var.instance_count
}
```

[top](#index)

### Outputs

```terraform
output "end_time" {
  description = "returns a string"
  value       = tencentcloud_reserved_instance.this.end_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_reserved_instance.this.id
}

output "start_time" {
  description = "returns a string"
  value       = tencentcloud_reserved_instance.this.start_time
}

output "status" {
  description = "returns a string"
  value       = tencentcloud_reserved_instance.this.status
}

output "this" {
  value = tencentcloud_reserved_instance.this
}
```

[top](#index)