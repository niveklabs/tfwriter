# linode_sshkey

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/linode/d/linode_sshkey"

  # label - (required) is a type of string
  label = null
}
```

[top](#index)

### Variables

```terraform
variable "label" {
  description = "(required) - The label of the Linode SSH Key."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "linode_sshkey" "this" {
  # label - (required) is a type of string
  label = var.label
}
```

[top](#index)

### Outputs

```terraform
output "created" {
  description = "returns a string"
  value       = data.linode_sshkey.this.created
}

output "id" {
  description = "returns a string"
  value       = data.linode_sshkey.this.id
}

output "ssh_key" {
  description = "returns a string"
  value       = data.linode_sshkey.this.ssh_key
}

output "this" {
  value = linode_sshkey.this
}
```

[top](#index)