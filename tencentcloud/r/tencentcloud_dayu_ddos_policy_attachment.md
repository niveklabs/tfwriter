# tencentcloud_dayu_ddos_policy_attachment

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
module "tencentcloud_dayu_ddos_policy_attachment" {
  source = "./modules/tencentcloud/r/tencentcloud_dayu_ddos_policy_attachment"

  # policy_id - (required) is a type of string
  policy_id = null
  # resource_id - (required) is a type of string
  resource_id = null
  # resource_type - (required) is a type of string
  resource_type = null
}
```

[top](#index)

### Variables

```terraform
variable "policy_id" {
  description = "(required) - ID of the policy."
  type        = string
}

variable "resource_id" {
  description = "(required) - ID of the attached resource."
  type        = string
}

variable "resource_type" {
  description = "(required) - Type of the resource that the DDoS policy works for. Valid values are `bgpip`, `bgp`, `bgp-multip`, `net`."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_dayu_ddos_policy_attachment" "this" {
  policy_id     = var.policy_id
  resource_id   = var.resource_id
  resource_type = var.resource_type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_dayu_ddos_policy_attachment.this.id
}

output "this" {
  value = tencentcloud_dayu_ddos_policy_attachment.this
}
```

[top](#index)