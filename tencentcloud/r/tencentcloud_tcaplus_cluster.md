# tencentcloud_tcaplus_cluster

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_tcaplus_cluster" {
  source = "./modules/tencentcloud/r/tencentcloud_tcaplus_cluster"

  # cluster_name - (required) is a type of string
  cluster_name = null
  # idl_type - (required) is a type of string
  idl_type = null
  # old_password_expire_last - (optional) is a type of number
  old_password_expire_last = null
  # password - (required) is a type of string
  password = null
  # subnet_id - (required) is a type of string
  subnet_id = null
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_name" {
  description = "(required) - Name of the TcaplusDB cluster. Name length should be between 1 and 30."
  type        = string
}

variable "idl_type" {
  description = "(required) - IDL type of the TcaplusDB cluster. Valid values: `PROTO` and `TDR`."
  type        = string
}

variable "old_password_expire_last" {
  description = "(optional) - Expiration time of old password after password update, unit: second."
  type        = number
  default     = null
}

variable "password" {
  description = "(required) - Password of the TcaplusDB cluster. Password length should be between 12 and 16. The password must be a *mix* of uppercase letters (A-Z), lowercase *letters* (a-z) and *numbers* (0-9)."
  type        = string
}

variable "subnet_id" {
  description = "(required) - Subnet id of the TcaplusDB cluster."
  type        = string
}

variable "vpc_id" {
  description = "(required) - VPC id of the TcaplusDB cluster."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_tcaplus_cluster" "this" {
  # cluster_name - (required) is a type of string
  cluster_name = var.cluster_name
  # idl_type - (required) is a type of string
  idl_type = var.idl_type
  # old_password_expire_last - (optional) is a type of number
  old_password_expire_last = var.old_password_expire_last
  # password - (required) is a type of string
  password = var.password
  # subnet_id - (required) is a type of string
  subnet_id = var.subnet_id
  # vpc_id - (required) is a type of string
  vpc_id = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "api_access_id" {
  description = "returns a string"
  value       = tencentcloud_tcaplus_cluster.this.api_access_id
}

output "api_access_ip" {
  description = "returns a string"
  value       = tencentcloud_tcaplus_cluster.this.api_access_ip
}

output "api_access_port" {
  description = "returns a number"
  value       = tencentcloud_tcaplus_cluster.this.api_access_port
}

output "create_time" {
  description = "returns a string"
  value       = tencentcloud_tcaplus_cluster.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_tcaplus_cluster.this.id
}

output "network_type" {
  description = "returns a string"
  value       = tencentcloud_tcaplus_cluster.this.network_type
}

output "old_password_expire_time" {
  description = "returns a string"
  value       = tencentcloud_tcaplus_cluster.this.old_password_expire_time
}

output "password_status" {
  description = "returns a string"
  value       = tencentcloud_tcaplus_cluster.this.password_status
}

output "this" {
  value = tencentcloud_tcaplus_cluster.this
}
```

[top](#index)