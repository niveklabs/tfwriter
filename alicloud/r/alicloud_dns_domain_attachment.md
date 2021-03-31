# alicloud_dns_domain_attachment

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
module "alicloud_dns_domain_attachment" {
  source = "./modules/alicloud/r/alicloud_dns_domain_attachment"

  # domain_names - (required) is a type of set of string
  domain_names = []
  # instance_id - (required) is a type of string
  instance_id = null
}
```

[top](#index)

### Variables

```terraform
variable "domain_names" {
  description = "(required)"
  type        = set(string)
}

variable "instance_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_dns_domain_attachment" "this" {
  domain_names = var.domain_names
  instance_id  = var.instance_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_dns_domain_attachment.this.id
}

output "this" {
  value = alicloud_dns_domain_attachment.this
}
```

[top](#index)