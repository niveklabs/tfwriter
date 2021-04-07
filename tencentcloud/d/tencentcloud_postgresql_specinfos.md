# tencentcloud_postgresql_specinfos

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
module "tencentcloud_postgresql_specinfos" {
  source = "./modules/tencentcloud/d/tencentcloud_postgresql_specinfos"

  # availability_zone - (required) is a type of string
  availability_zone = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(required) - The zone of the postgresql instance to query."
  type        = string
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
data "tencentcloud_postgresql_specinfos" "this" {
  # availability_zone - (required) is a type of string
  availability_zone = var.availability_zone
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_postgresql_specinfos.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_postgresql_specinfos.this.list
}

output "this" {
  value = tencentcloud_postgresql_specinfos.this
}
```

[top](#index)