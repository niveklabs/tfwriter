# tencentcloud_tcr_token

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
module "tencentcloud_tcr_token" {
  source = "./modules/tencentcloud/r/tencentcloud_tcr_token"

  # description - (optional) is a type of string
  description = null
  # enable - (optional) is a type of bool
  enable = null
  # instance_id - (required) is a type of string
  instance_id = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of the token. Valid length is [0~255]."
  type        = string
  default     = null
}

variable "enable" {
  description = "(optional) - Indicate to enable this token or not."
  type        = bool
  default     = null
}

variable "instance_id" {
  description = "(required) - ID of the TCR instance."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_tcr_token" "this" {
  description = var.description
  enable      = var.enable
  instance_id = var.instance_id
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_tcr_token.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_tcr_token.this.id
}

output "token" {
  description = "returns a string"
  value       = tencentcloud_tcr_token.this.token
}

output "token_id" {
  description = "returns a string"
  value       = tencentcloud_tcr_token.this.token_id
}

output "user_name" {
  description = "returns a string"
  value       = tencentcloud_tcr_token.this.user_name
}

output "this" {
  value = tencentcloud_tcr_token.this
}
```

[top](#index)