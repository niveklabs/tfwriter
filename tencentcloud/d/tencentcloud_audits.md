# tencentcloud_audits

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
module "tencentcloud_audits" {
  source = "./modules/tencentcloud/d/tencentcloud_audits"

  # name - (optional) is a type of string
  name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Name of the audits."
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
data "tencentcloud_audits" "this" {
  # name - (optional) is a type of string
  name = var.name
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "audit_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_audits.this.audit_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_audits.this.id
}

output "this" {
  value = tencentcloud_audits.this
}
```

[top](#index)