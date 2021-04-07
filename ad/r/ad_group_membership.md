# ad_group_membership

[back](../ad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ad = ">= 0.4.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ad_group_membership" {
  source = "./modules/ad/r/ad_group_membership"

  # group_id - (required) is a type of string
  group_id = null
  # group_members - (required) is a type of set of string
  group_members = []
}
```

[top](#index)

### Variables

```terraform
variable "group_id" {
  description = "(required) - The ID of the group. This can be a GUID, a SID, a Distinguished Name, or the SAM Account Name of the group."
  type        = string
}

variable "group_members" {
  description = "(required) - A list of member AD Principals. Each principal can be identified by its GUID, SID, Distinguished Name, or SAM Account Name. Only one is required"
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "ad_group_membership" "this" {
  # group_id - (required) is a type of string
  group_id = var.group_id
  # group_members - (required) is a type of set of string
  group_members = var.group_members
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ad_group_membership.this.id
}

output "this" {
  value = ad_group_membership.this
}
```

[top](#index)