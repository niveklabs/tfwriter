# tencentcloud_ckafka_user

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
module "tencentcloud_ckafka_user" {
  source = "./modules/tencentcloud/r/tencentcloud_ckafka_user"

  # account_name - (required) is a type of string
  account_name = null
  # instance_id - (required) is a type of string
  instance_id = null
  # password - (required) is a type of string
  password = null
}
```

[top](#index)

### Variables

```terraform
variable "account_name" {
  description = "(required) - Account name used to access to ckafka instance."
  type        = string
}

variable "instance_id" {
  description = "(required) - ID of the ckafka instance."
  type        = string
}

variable "password" {
  description = "(required) - Password of the account."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_ckafka_user" "this" {
  # account_name - (required) is a type of string
  account_name = var.account_name
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
  # password - (required) is a type of string
  password = var.password
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_ckafka_user.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_ckafka_user.this.id
}

output "update_time" {
  description = "returns a string"
  value       = tencentcloud_ckafka_user.this.update_time
}

output "this" {
  value = tencentcloud_ckafka_user.this
}
```

[top](#index)