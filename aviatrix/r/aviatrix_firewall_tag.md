# aviatrix_firewall_tag

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.17.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_firewall_tag" {
  source = "./modules/aviatrix/r/aviatrix_firewall_tag"

  # firewall_tag - (required) is a type of string
  firewall_tag = null

  cidr_list = [{
    cidr          = null
    cidr_tag_name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "firewall_tag" {
  description = "(required) - This parameter represents the name of a Cloud-Account in Aviatrix controller."
  type        = string
}

variable "cidr_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      cidr          = string
      cidr_tag_name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_firewall_tag" "this" {
  firewall_tag = var.firewall_tag

  dynamic "cidr_list" {
    for_each = var.cidr_list
    content {
      cidr          = cidr_list.value["cidr"]
      cidr_tag_name = cidr_list.value["cidr_tag_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_firewall_tag.this.id
}

output "this" {
  value = aviatrix_firewall_tag.this
}
```

[top](#index)