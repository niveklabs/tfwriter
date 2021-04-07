# tencentcloud_audit_key_alias

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
module "tencentcloud_audit_key_alias" {
  source = "./modules/tencentcloud/d/tencentcloud_audit_key_alias"

  # region - (required) is a type of string
  region = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "region" {
  description = "(required) - Region."
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
data "tencentcloud_audit_key_alias" "this" {
  region             = var.region
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "audit_key_alias_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_audit_key_alias.this.audit_key_alias_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_audit_key_alias.this.id
}

output "this" {
  value = tencentcloud_audit_key_alias.this
}
```

[top](#index)