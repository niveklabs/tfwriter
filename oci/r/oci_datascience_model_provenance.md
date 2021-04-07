# oci_datascience_model_provenance

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_datascience_model_provenance" {
  source = "./modules/oci/r/oci_datascience_model_provenance"

  # git_branch - (optional) is a type of string
  git_branch = null
  # git_commit - (optional) is a type of string
  git_commit = null
  # model_id - (required) is a type of string
  model_id = null
  # repository_url - (optional) is a type of string
  repository_url = null
  # script_dir - (optional) is a type of string
  script_dir = null
  # training_script - (optional) is a type of string
  training_script = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "git_branch" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "git_commit" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "model_id" {
  description = "(required)"
  type        = string
}

variable "repository_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "script_dir" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "training_script" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_datascience_model_provenance" "this" {
  # git_branch - (optional) is a type of string
  git_branch = var.git_branch
  # git_commit - (optional) is a type of string
  git_commit = var.git_commit
  # model_id - (required) is a type of string
  model_id = var.model_id
  # repository_url - (optional) is a type of string
  repository_url = var.repository_url
  # script_dir - (optional) is a type of string
  script_dir = var.script_dir
  # training_script - (optional) is a type of string
  training_script = var.training_script

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "git_branch" {
  description = "returns a string"
  value       = oci_datascience_model_provenance.this.git_branch
}

output "git_commit" {
  description = "returns a string"
  value       = oci_datascience_model_provenance.this.git_commit
}

output "id" {
  description = "returns a string"
  value       = oci_datascience_model_provenance.this.id
}

output "repository_url" {
  description = "returns a string"
  value       = oci_datascience_model_provenance.this.repository_url
}

output "script_dir" {
  description = "returns a string"
  value       = oci_datascience_model_provenance.this.script_dir
}

output "training_script" {
  description = "returns a string"
  value       = oci_datascience_model_provenance.this.training_script
}

output "this" {
  value = oci_datascience_model_provenance.this
}
```

[top](#index)