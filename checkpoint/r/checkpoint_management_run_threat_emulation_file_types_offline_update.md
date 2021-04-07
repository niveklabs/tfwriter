# checkpoint_management_run_threat_emulation_file_types_offline_update

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_run_threat_emulation_file_types_offline_update" {
  source = "./modules/checkpoint/r/checkpoint_management_run_threat_emulation_file_types_offline_update"

  # file_path - (required) is a type of string
  file_path = null
  # file_raw_data - (required) is a type of string
  file_raw_data = null
}
```

[top](#index)

### Variables

```terraform
variable "file_path" {
  description = "(required) - File path for offline update of Threat Emulation file types, the file path should be on the management machine."
  type        = string
}

variable "file_raw_data" {
  description = "(required) - The contents of a file containing the Threat Emulation file types."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_run_threat_emulation_file_types_offline_update" "this" {
  # file_path - (required) is a type of string
  file_path = var.file_path
  # file_raw_data - (required) is a type of string
  file_raw_data = var.file_raw_data
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_run_threat_emulation_file_types_offline_update.this.id
}

output "this" {
  value = checkpoint_management_run_threat_emulation_file_types_offline_update.this
}
```

[top](#index)