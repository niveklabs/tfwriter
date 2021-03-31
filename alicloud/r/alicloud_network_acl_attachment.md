# alicloud_network_acl_attachment

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_network_acl_attachment" {
  source = "./modules/alicloud/r/alicloud_network_acl_attachment"

  # network_acl_id - (required) is a type of string
  network_acl_id = null

  resources = [{
    resource_id   = null
    resource_type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "network_acl_id" {
  description = "(required)"
  type        = string
}

variable "resources" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      resource_id   = string
      resource_type = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_network_acl_attachment" "this" {
  network_acl_id = var.network_acl_id

  dynamic "resources" {
    for_each = var.resources
    content {
      resource_id   = resources.value["resource_id"]
      resource_type = resources.value["resource_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_network_acl_attachment.this.id
}

output "this" {
  value = alicloud_network_acl_attachment.this
}
```

[top](#index)