# tencentcloud_security_group

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
module "tencentcloud_security_group" {
  source = "./modules/tencentcloud/d/tencentcloud_security_group"

  # name - (optional) is a type of string
  name = null
  # security_group_id - (optional) is a type of string
  security_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Name of the security group to be queried. Conflict with `security_group_id`."
  type        = string
  default     = null
}

variable "security_group_id" {
  description = "(optional) - ID of the security group to be queried. Conflict with `name`."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_security_group" "this" {
  # name - (optional) is a type of string
  name = var.name
  # security_group_id - (optional) is a type of string
  security_group_id = var.security_group_id
}
```

[top](#index)

### Outputs

```terraform
output "be_associate_count" {
  description = "returns a number"
  value       = data.tencentcloud_security_group.this.be_associate_count
}

output "create_time" {
  description = "returns a string"
  value       = data.tencentcloud_security_group.this.create_time
}

output "description" {
  description = "returns a string"
  value       = data.tencentcloud_security_group.this.description
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_security_group.this.id
}

output "project_id" {
  description = "returns a number"
  value       = data.tencentcloud_security_group.this.project_id
}

output "this" {
  value = tencentcloud_security_group.this
}
```

[top](#index)