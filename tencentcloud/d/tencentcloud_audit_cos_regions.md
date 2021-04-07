# tencentcloud_audit_cos_regions

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
module "tencentcloud_audit_cos_regions" {
  source = "./modules/tencentcloud/d/tencentcloud_audit_cos_regions"

  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_audit_cos_regions" "this" {
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "audit_cos_region_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_audit_cos_regions.this.audit_cos_region_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_audit_cos_regions.this.id
}

output "this" {
  value = tencentcloud_audit_cos_regions.this
}
```

[top](#index)