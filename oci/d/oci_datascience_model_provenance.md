# oci_datascience_model_provenance

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_datascience_model_provenance" {
  source = "./modules/oci/d/oci_datascience_model_provenance"

  # model_id - (required) is a type of string
  model_id = null
}
```

[top](#index)

### Variables

```terraform
variable "model_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_datascience_model_provenance" "this" {
  model_id = var.model_id
}
```

[top](#index)

### Outputs

```terraform
output "git_branch" {
  description = "returns a string"
  value       = data.oci_datascience_model_provenance.this.git_branch
}

output "git_commit" {
  description = "returns a string"
  value       = data.oci_datascience_model_provenance.this.git_commit
}

output "id" {
  description = "returns a string"
  value       = data.oci_datascience_model_provenance.this.id
}

output "repository_url" {
  description = "returns a string"
  value       = data.oci_datascience_model_provenance.this.repository_url
}

output "script_dir" {
  description = "returns a string"
  value       = data.oci_datascience_model_provenance.this.script_dir
}

output "training_script" {
  description = "returns a string"
  value       = data.oci_datascience_model_provenance.this.training_script
}

output "this" {
  value = oci_datascience_model_provenance.this
}
```

[top](#index)