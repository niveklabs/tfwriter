# scaleway_account_ssh_key

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_account_ssh_key" {
  source = "./modules/scaleway/d/scaleway_account_ssh_key"

  # name - (optional) is a type of string
  name = null
  # ssh_key_id - (optional) is a type of string
  ssh_key_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - The name of the SSH key"
  type        = string
  default     = null
}

variable "ssh_key_id" {
  description = "(optional) - The ID of the SSH key"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "scaleway_account_ssh_key" "this" {
  name       = var.name
  ssh_key_id = var.ssh_key_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.scaleway_account_ssh_key.this.id
}

output "organization_id" {
  description = "returns a string"
  value       = data.scaleway_account_ssh_key.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = data.scaleway_account_ssh_key.this.project_id
}

output "public_key" {
  description = "returns a string"
  value       = data.scaleway_account_ssh_key.this.public_key
}

output "this" {
  value = scaleway_account_ssh_key.this
}
```

[top](#index)