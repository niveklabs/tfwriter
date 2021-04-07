# tencentcloud_reserved_instances

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "tencentcloud_reserved_instances" {
  source = "./modules/tencentcloud/d/tencentcloud_reserved_instances"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # instance_type - (optional) is a type of string
  instance_type = null
  # reserved_instance_id - (optional) is a type of string
  reserved_instance_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(optional) - The available zone that the reserved instance locates at."
  type        = string
  default     = null
}

variable "instance_type" {
  description = "(optional) - The type of reserved instance."
  type        = string
  default     = null
}

variable "reserved_instance_id" {
  description = "(optional) - ID of the reserved instance to be query."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_reserved_instances" "this" {
  availability_zone    = var.availability_zone
  instance_type        = var.instance_type
  reserved_instance_id = var.reserved_instance_id
  result_output_file   = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_reserved_instances.this.id
}

output "reserved_instance_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_reserved_instances.this.reserved_instance_list
}

output "this" {
  value = tencentcloud_reserved_instances.this
}
```

[top](#index)