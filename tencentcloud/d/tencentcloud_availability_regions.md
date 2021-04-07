# tencentcloud_availability_regions

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
module "tencentcloud_availability_regions" {
  source = "./modules/tencentcloud/d/tencentcloud_availability_regions"

  # include_unavailable - (optional) is a type of bool
  include_unavailable = null
  # name - (optional) is a type of string
  name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "include_unavailable" {
  description = "(optional) - A bool variable indicates that the query will include `UNAVAILABLE` regions."
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional) - When specified, only the region with the exactly name match will be returned. `default` value means it consistent with the provider region."
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
data "tencentcloud_availability_regions" "this" {
  include_unavailable = var.include_unavailable
  name                = var.name
  result_output_file  = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_availability_regions.this.id
}

output "regions" {
  description = "returns a list of object"
  value       = data.tencentcloud_availability_regions.this.regions
}

output "this" {
  value = tencentcloud_availability_regions.this
}
```

[top](#index)