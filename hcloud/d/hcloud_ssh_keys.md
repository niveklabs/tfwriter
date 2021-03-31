# hcloud_ssh_keys

[back](../hcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcloud = ">= 1.26.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcloud_ssh_keys" {
  source = "./modules/hcloud/d/hcloud_ssh_keys"

  # with_selector - (optional) is a type of string
  with_selector = null
}
```

[top](#index)

### Variables

```terraform
variable "with_selector" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "hcloud_ssh_keys" "this" {
  with_selector = var.with_selector
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.hcloud_ssh_keys.this.id
}

output "ssh_keys" {
  description = "returns a list of object"
  value       = data.hcloud_ssh_keys.this.ssh_keys
}

output "this" {
  value = hcloud_ssh_keys.this
}
```

[top](#index)