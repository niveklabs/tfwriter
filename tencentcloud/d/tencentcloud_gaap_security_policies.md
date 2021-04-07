# tencentcloud_gaap_security_policies

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
module "tencentcloud_gaap_security_policies" {
  source = "./modules/tencentcloud/d/tencentcloud_gaap_security_policies"

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
data "tencentcloud_gaap_security_policies" "this" {
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "action" {
  description = "returns a string"
  value       = data.tencentcloud_gaap_security_policies.this.action
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_gaap_security_policies.this.id
}

output "proxy_id" {
  description = "returns a string"
  value       = data.tencentcloud_gaap_security_policies.this.proxy_id
}

output "status" {
  description = "returns a string"
  value       = data.tencentcloud_gaap_security_policies.this.status
}

output "this" {
  value = tencentcloud_gaap_security_policies.this
}
```

[top](#index)