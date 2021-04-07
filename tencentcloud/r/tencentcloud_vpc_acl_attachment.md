# tencentcloud_vpc_acl_attachment

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
module "tencentcloud_vpc_acl_attachment" {
  source = "./modules/tencentcloud/r/tencentcloud_vpc_acl_attachment"

  # acl_id - (required) is a type of string
  acl_id = null
  # subnet_id - (required) is a type of string
  subnet_id = null
}
```

[top](#index)

### Variables

```terraform
variable "acl_id" {
  description = "(required) - ID of the attached ACL."
  type        = string
}

variable "subnet_id" {
  description = "(required) - The Subnet instance ID."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_vpc_acl_attachment" "this" {
  acl_id    = var.acl_id
  subnet_id = var.subnet_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_vpc_acl_attachment.this.id
}

output "this" {
  value = tencentcloud_vpc_acl_attachment.this
}
```

[top](#index)