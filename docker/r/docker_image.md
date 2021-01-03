# docker_image

[back](../docker.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    docker = ">= 2.7.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "docker_image" {
  source = "./modules/docker/r/docker_image"

  # keep_locally - (optional) is a type of bool
  keep_locally = null
  # name - (required) is a type of string
  name = null
  # pull_trigger - (optional) is a type of string
  pull_trigger = null
  # pull_triggers - (optional) is a type of set of string
  pull_triggers = []
}
```

[top](#index)

### Variables

```terraform
variable "keep_locally" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "pull_trigger" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pull_triggers" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "docker_image" "this" {
  keep_locally  = var.keep_locally
  name          = var.name
  pull_trigger  = var.pull_trigger
  pull_triggers = var.pull_triggers
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = docker_image.this.id
}

output "latest" {
  description = "returns a string"
  value       = docker_image.this.latest
}

output "this" {
  value = docker_image.this
}
```

[top](#index)