# tencentcloud_cfs_access_rule

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
module "tencentcloud_cfs_access_rule" {
  source = "./modules/tencentcloud/r/tencentcloud_cfs_access_rule"

  # access_group_id - (required) is a type of string
  access_group_id = null
  # auth_client_ip - (required) is a type of string
  auth_client_ip = null
  # priority - (required) is a type of number
  priority = null
  # rw_permission - (optional) is a type of string
  rw_permission = null
  # user_permission - (optional) is a type of string
  user_permission = null
}
```

[top](#index)

### Variables

```terraform
variable "access_group_id" {
  description = "(required) - ID of a access group."
  type        = string
}

variable "auth_client_ip" {
  description = "(required) - A single IP or a single IP address range such as 10.1.10.11 or 10.10.1.0/24 indicates that all IPs are allowed. Please note that the IP entered should be CVM's private IP."
  type        = string
}

variable "priority" {
  description = "(required) - The priority level of rule. Valid value ranges: (1~100). `1` indicates the highest priority."
  type        = number
}

variable "rw_permission" {
  description = "(optional) - Read and write permissions. Valid values are `RO` and `RW`. and default is `RO`."
  type        = string
  default     = null
}

variable "user_permission" {
  description = "(optional) - The permissions of accessing users. Valid values are `all_squash`, `no_all_squash`, `root_squash` and `no_root_squash`. and default is `root_squash`. `all_squash` indicates that all access users are mapped as anonymous users or user groups; `no_all_squash` indicates that access users will match local users first and be mapped to anonymous users or user groups after matching failed; `root_squash` indicates that map access root users to anonymous users or user groups; `no_root_squash` indicates that access root users keep root account permission."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_cfs_access_rule" "this" {
  # access_group_id - (required) is a type of string
  access_group_id = var.access_group_id
  # auth_client_ip - (required) is a type of string
  auth_client_ip = var.auth_client_ip
  # priority - (required) is a type of number
  priority = var.priority
  # rw_permission - (optional) is a type of string
  rw_permission = var.rw_permission
  # user_permission - (optional) is a type of string
  user_permission = var.user_permission
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_cfs_access_rule.this.id
}

output "this" {
  value = tencentcloud_cfs_access_rule.this
}
```

[top](#index)