# alicloud_db_database

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_db_database" {
  source = "./modules/alicloud/r/alicloud_db_database"

  # character_set - (optional) is a type of string
  character_set = null
  # description - (optional) is a type of string
  description = null
  # instance_id - (required) is a type of string
  instance_id = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "character_set" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_db_database" "this" {
  # character_set - (optional) is a type of string
  character_set = var.character_set
  # description - (optional) is a type of string
  description = var.description
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_db_database.this.id
}

output "this" {
  value = alicloud_db_database.this
}
```

[top](#index)