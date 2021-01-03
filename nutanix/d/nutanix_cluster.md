# nutanix_cluster

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nutanix = ">= 1.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nutanix_cluster" {
  source = "./modules/nutanix/d/nutanix_cluster"

  # cluster_id - (optional) is a type of string
  cluster_id = null
  # name - (optional) is a type of string
  name = null

  categories = [{
    name  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "categories" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "nutanix_cluster" "this" {
  cluster_id = var.cluster_id
  name       = var.name

  dynamic "categories" {
    for_each = var.categories
    content {
      name  = categories.value["name"]
      value = categories.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "analysis_vm_efficiency_map" {
  description = "returns a map of string"
  value       = data.nutanix_cluster.this.analysis_vm_efficiency_map
}

output "api_version" {
  description = "returns a string"
  value       = data.nutanix_cluster.this.api_version
}

output "authorized_public_key_list" {
  description = "returns a list of object"
  value       = data.nutanix_cluster.this.authorized_public_key_list
}

output "build" {
  description = "returns a map of string"
  value       = data.nutanix_cluster.this.build
}

output "ca_certificate_list" {
  description = "returns a list of object"
  value       = data.nutanix_cluster.this.ca_certificate_list
}

output "certification_signing_info" {
  description = "returns a map of string"
  value       = data.nutanix_cluster.this.certification_signing_info
}

output "client_auth" {
  description = "returns a map of string"
  value       = data.nutanix_cluster.this.client_auth
}

output "cluster_arch" {
  description = "returns a string"
  value       = data.nutanix_cluster.this.cluster_arch
}

output "cluster_id" {
  description = "returns a string"
  value       = data.nutanix_cluster.this.cluster_id
}

output "domain_server_credentials" {
  description = "returns a map of string"
  value       = data.nutanix_cluster.this.domain_server_credentials
}

output "domain_server_name" {
  description = "returns a string"
  value       = data.nutanix_cluster.this.domain_server_name
}

output "domain_server_nameserver" {
  description = "returns a string"
  value       = data.nutanix_cluster.this.domain_server_nameserver
}

output "enabled_feature_list" {
  description = "returns a list of string"
  value       = data.nutanix_cluster.this.enabled_feature_list
}

output "encryption_status" {
  description = "returns a string"
  value       = data.nutanix_cluster.this.encryption_status
}

output "external_data_services_ip" {
  description = "returns a string"
  value       = data.nutanix_cluster.this.external_data_services_ip
}

output "external_ip" {
  description = "returns a string"
  value       = data.nutanix_cluster.this.external_ip
}

output "external_subnet" {
  description = "returns a string"
  value       = data.nutanix_cluster.this.external_subnet
}

output "gpu_driver_version" {
  description = "returns a string"
  value       = data.nutanix_cluster.this.gpu_driver_version
}

output "http_proxy_list" {
  description = "returns a list of object"
  value       = data.nutanix_cluster.this.http_proxy_list
}

output "http_proxy_whitelist" {
  description = "returns a list of object"
  value       = data.nutanix_cluster.this.http_proxy_whitelist
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_cluster.this.id
}

output "internal_subnet" {
  description = "returns a string"
  value       = data.nutanix_cluster.this.internal_subnet
}

output "is_available" {
  description = "returns a bool"
  value       = data.nutanix_cluster.this.is_available
}

output "management_server_list" {
  description = "returns a list of object"
  value       = data.nutanix_cluster.this.management_server_list
}

output "masquerading_ip" {
  description = "returns a string"
  value       = data.nutanix_cluster.this.masquerading_ip
}

output "masquerading_port" {
  description = "returns a number"
  value       = data.nutanix_cluster.this.masquerading_port
}

output "metadata" {
  description = "returns a map of string"
  value       = data.nutanix_cluster.this.metadata
}

output "name" {
  description = "returns a string"
  value       = data.nutanix_cluster.this.name
}

output "name_server_ip_list" {
  description = "returns a list of string"
  value       = data.nutanix_cluster.this.name_server_ip_list
}

output "nfs_subnet_whitelist" {
  description = "returns a list of string"
  value       = data.nutanix_cluster.this.nfs_subnet_whitelist
}

output "nodes" {
  description = "returns a list of object"
  value       = data.nutanix_cluster.this.nodes
}

output "ntp_server_ip_list" {
  description = "returns a list of string"
  value       = data.nutanix_cluster.this.ntp_server_ip_list
}

output "operation_mode" {
  description = "returns a string"
  value       = data.nutanix_cluster.this.operation_mode
}

output "owner_reference" {
  description = "returns a map of string"
  value       = data.nutanix_cluster.this.owner_reference
}

output "project_reference" {
  description = "returns a map of string"
  value       = data.nutanix_cluster.this.project_reference
}

output "service_list" {
  description = "returns a list of string"
  value       = data.nutanix_cluster.this.service_list
}

output "smtp_server_address" {
  description = "returns a map of string"
  value       = data.nutanix_cluster.this.smtp_server_address
}

output "smtp_server_credentials" {
  description = "returns a map of string"
  value       = data.nutanix_cluster.this.smtp_server_credentials
}

output "smtp_server_email_address" {
  description = "returns a string"
  value       = data.nutanix_cluster.this.smtp_server_email_address
}

output "smtp_server_proxy_type_list" {
  description = "returns a list of string"
  value       = data.nutanix_cluster.this.smtp_server_proxy_type_list
}

output "smtp_server_type" {
  description = "returns a string"
  value       = data.nutanix_cluster.this.smtp_server_type
}

output "software_map_ncc" {
  description = "returns a map of string"
  value       = data.nutanix_cluster.this.software_map_ncc
}

output "software_map_nos" {
  description = "returns a map of string"
  value       = data.nutanix_cluster.this.software_map_nos
}

output "ssl_key_expire_datetime" {
  description = "returns a string"
  value       = data.nutanix_cluster.this.ssl_key_expire_datetime
}

output "ssl_key_name" {
  description = "returns a string"
  value       = data.nutanix_cluster.this.ssl_key_name
}

output "ssl_key_signing_info" {
  description = "returns a map of string"
  value       = data.nutanix_cluster.this.ssl_key_signing_info
}

output "ssl_key_type" {
  description = "returns a string"
  value       = data.nutanix_cluster.this.ssl_key_type
}

output "state" {
  description = "returns a string"
  value       = data.nutanix_cluster.this.state
}

output "supported_information_verbosity" {
  description = "returns a string"
  value       = data.nutanix_cluster.this.supported_information_verbosity
}

output "timezone" {
  description = "returns a string"
  value       = data.nutanix_cluster.this.timezone
}

output "this" {
  value = nutanix_cluster.this
}
```

[top](#index)