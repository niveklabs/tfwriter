# tencentcloud_dc_instances

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
module "tencentcloud_dc_instances" {
  source = "./modules/tencentcloud/d/tencentcloud_dc_instances"

  # dc_id - (optional) is a type of string
  dc_id = null
  # name - (optional) is a type of string
  name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "dc_id" {
  description = "(optional) - ID of the DC to be queried."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of the DC to be queried."
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
data "tencentcloud_dc_instances" "this" {
  dc_id              = var.dc_id
  name               = var.name
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_dc_instances.this.id
}

output "instance_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_dc_instances.this.instance_list
}

output "this" {
  value = tencentcloud_dc_instances.this
}
```

[top](#index)