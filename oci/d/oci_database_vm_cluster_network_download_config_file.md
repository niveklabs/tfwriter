# oci_database_vm_cluster_network_download_config_file

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_vm_cluster_network_download_config_file" {
  source = "./modules/oci/d/oci_database_vm_cluster_network_download_config_file"

  # base64_encode_content - (optional) is a type of bool
  base64_encode_content = null
  # exadata_infrastructure_id - (required) is a type of string
  exadata_infrastructure_id = null
  # vm_cluster_network_id - (required) is a type of string
  vm_cluster_network_id = null
}
```

[top](#index)

### Variables

```terraform
variable "base64_encode_content" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "exadata_infrastructure_id" {
  description = "(required)"
  type        = string
}

variable "vm_cluster_network_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_vm_cluster_network_download_config_file" "this" {
  base64_encode_content     = var.base64_encode_content
  exadata_infrastructure_id = var.exadata_infrastructure_id
  vm_cluster_network_id     = var.vm_cluster_network_id
}
```

[top](#index)

### Outputs

```terraform
output "content" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_network_download_config_file.this.content
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_network_download_config_file.this.id
}

output "this" {
  value = oci_database_vm_cluster_network_download_config_file.this
}
```

[top](#index)