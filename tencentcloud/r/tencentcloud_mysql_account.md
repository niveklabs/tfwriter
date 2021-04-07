# tencentcloud_mysql_account

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
module "tencentcloud_mysql_account" {
  source = "./modules/tencentcloud/r/tencentcloud_mysql_account"

  # description - (optional) is a type of string
  description = null
  # host - (optional) is a type of string
  host = null
  # mysql_id - (required) is a type of string
  mysql_id = null
  # name - (required) is a type of string
  name = null
  # password - (required) is a type of string
  password = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Database description."
  type        = string
  default     = null
}

variable "host" {
  description = "(optional) - Account host, default is `%`."
  type        = string
  default     = null
}

variable "mysql_id" {
  description = "(required) - Instance ID to which the account belongs."
  type        = string
}

variable "name" {
  description = "(required) - Account name."
  type        = string
}

variable "password" {
  description = "(required) - Operation password."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_mysql_account" "this" {
  # description - (optional) is a type of string
  description = var.description
  # host - (optional) is a type of string
  host = var.host
  # mysql_id - (required) is a type of string
  mysql_id = var.mysql_id
  # name - (required) is a type of string
  name = var.name
  # password - (required) is a type of string
  password = var.password
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_mysql_account.this.id
}

output "this" {
  value = tencentcloud_mysql_account.this
}
```

[top](#index)