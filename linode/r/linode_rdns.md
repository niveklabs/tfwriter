# linode_rdns

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    linode = ">= 1.16.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_rdns" {
  source = "./modules/linode/r/linode_rdns"

  # address - (required) is a type of string
  address = null
  # rdns - (required) is a type of string
  rdns = null
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(required) - The public Linode IPv4 or IPv6 address to operate on."
  type        = string
}

variable "rdns" {
  description = "(required) - The reverse DNS assigned to this address. For public IPv4 addresses, this will be set to a default value provided by Linode if not explicitly set."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "linode_rdns" "this" {
  address = var.address
  rdns    = var.rdns
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = linode_rdns.this.id
}

output "this" {
  value = linode_rdns.this
}
```

[top](#index)