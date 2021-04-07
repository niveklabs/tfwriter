# tencentcloud_key_pair

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
module "tencentcloud_key_pair" {
  source = "./modules/tencentcloud/r/tencentcloud_key_pair"

  # key_name - (required) is a type of string
  key_name = null
  # project_id - (optional) is a type of number
  project_id = null
  # public_key - (required) is a type of string
  public_key = null
}
```

[top](#index)

### Variables

```terraform
variable "key_name" {
  description = "(required) - The key pair's name. It is the only in one TencentCloud account."
  type        = string
}

variable "project_id" {
  description = "(optional) - Specifys to which project the key pair belongs."
  type        = number
  default     = null
}

variable "public_key" {
  description = "(required) - You can import an existing public key and using TencentCloud key pair to manage it."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_key_pair" "this" {
  # key_name - (required) is a type of string
  key_name = var.key_name
  # project_id - (optional) is a type of number
  project_id = var.project_id
  # public_key - (required) is a type of string
  public_key = var.public_key
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_key_pair.this.id
}

output "this" {
  value = tencentcloud_key_pair.this
}
```

[top](#index)