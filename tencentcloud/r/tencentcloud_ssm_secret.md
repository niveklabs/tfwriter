# tencentcloud_ssm_secret

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
module "tencentcloud_ssm_secret" {
  source = "./modules/tencentcloud/r/tencentcloud_ssm_secret"

  # description - (optional) is a type of string
  description = null
  # is_enabled - (optional) is a type of bool
  is_enabled = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # recovery_window_in_days - (optional) is a type of number
  recovery_window_in_days = null
  # secret_name - (required) is a type of string
  secret_name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of secret. The maximum is 2048 bytes."
  type        = string
  default     = null
}

variable "is_enabled" {
  description = "(optional) - Specify whether to enable secret. Default value is `true`."
  type        = bool
  default     = null
}

variable "kms_key_id" {
  description = "(optional) - KMS keyId used to encrypt secret. If it is empty, it means that the CMK created by SSM for you by default is used for encryption. You can also specify the KMS CMK created by yourself in the same region for encryption."
  type        = string
  default     = null
}

variable "recovery_window_in_days" {
  description = "(optional) - Specify the scheduled deletion date. Default value is `0` that means to delete immediately. 1-30 means the number of days reserved, completely deleted after this date."
  type        = number
  default     = null
}

variable "secret_name" {
  description = "(required) - Name of secret which cannot be repeated in the same region. The maximum length is 128 bytes. The name can only contain English letters, numbers, underscore and hyphen '-'. The first character must be a letter or number."
  type        = string
}

variable "tags" {
  description = "(optional) - Tags of secret."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_ssm_secret" "this" {
  # description - (optional) is a type of string
  description = var.description
  # is_enabled - (optional) is a type of bool
  is_enabled = var.is_enabled
  # kms_key_id - (optional) is a type of string
  kms_key_id = var.kms_key_id
  # recovery_window_in_days - (optional) is a type of number
  recovery_window_in_days = var.recovery_window_in_days
  # secret_name - (required) is a type of string
  secret_name = var.secret_name
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_ssm_secret.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = tencentcloud_ssm_secret.this.kms_key_id
}

output "status" {
  description = "returns a string"
  value       = tencentcloud_ssm_secret.this.status
}

output "this" {
  value = tencentcloud_ssm_secret.this
}
```

[top](#index)