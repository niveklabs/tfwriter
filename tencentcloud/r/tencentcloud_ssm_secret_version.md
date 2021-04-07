# tencentcloud_ssm_secret_version

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
module "tencentcloud_ssm_secret_version" {
  source = "./modules/tencentcloud/r/tencentcloud_ssm_secret_version"

  # secret_binary - (optional) is a type of string
  secret_binary = null
  # secret_name - (required) is a type of string
  secret_name = null
  # secret_string - (optional) is a type of string
  secret_string = null
  # version_id - (required) is a type of string
  version_id = null
}
```

[top](#index)

### Variables

```terraform
variable "secret_binary" {
  description = "(optional) - The base64-encoded binary secret. secret_binary and secret_string must be set only one, and the maximum support is 4096 bytes. When secret status is `Disabled`, this field will not update anymore."
  type        = string
  default     = null
}

variable "secret_name" {
  description = "(required) - Name of secret which cannot be repeated in the same region. The maximum length is 128 bytes. The name can only contain English letters, numbers, underscore and hyphen '-'. The first character must be a letter or number."
  type        = string
}

variable "secret_string" {
  description = "(optional) - The string text of secret. secret_binary and secret_string must be set only one, and the maximum support is 4096 bytes. When secret status is `Disabled`, this field will not update anymore."
  type        = string
  default     = null
}

variable "version_id" {
  description = "(required) - Version of secret. The maximum length is 64 bytes. The version_id can only contain English letters, numbers, underscore and hyphen '-'. The first character must be a letter or number."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_ssm_secret_version" "this" {
  # secret_binary - (optional) is a type of string
  secret_binary = var.secret_binary
  # secret_name - (required) is a type of string
  secret_name = var.secret_name
  # secret_string - (optional) is a type of string
  secret_string = var.secret_string
  # version_id - (required) is a type of string
  version_id = var.version_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_ssm_secret_version.this.id
}

output "this" {
  value = tencentcloud_ssm_secret_version.this
}
```

[top](#index)