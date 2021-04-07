# linode_sshkey

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
module "linode_sshkey" {
  source = "./modules/linode/r/linode_sshkey"

  # label - (required) is a type of string
  label = null
  # ssh_key - (required) is a type of string
  ssh_key = null
}
```

[top](#index)

### Variables

```terraform
variable "label" {
  description = "(required) - The label of the Linode SSH Key."
  type        = string
}

variable "ssh_key" {
  description = "(required) - The public SSH Key, which is used to authenticate to the root user of the Linodes you deploy."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "linode_sshkey" "this" {
  # label - (required) is a type of string
  label = var.label
  # ssh_key - (required) is a type of string
  ssh_key = var.ssh_key
}
```

[top](#index)

### Outputs

```terraform
output "created" {
  description = "returns a string"
  value       = linode_sshkey.this.created
}

output "id" {
  description = "returns a string"
  value       = linode_sshkey.this.id
}

output "this" {
  value = linode_sshkey.this
}
```

[top](#index)