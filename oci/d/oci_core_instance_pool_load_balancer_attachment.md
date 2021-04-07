# oci_core_instance_pool_load_balancer_attachment

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_instance_pool_load_balancer_attachment" {
  source = "./modules/oci/d/oci_core_instance_pool_load_balancer_attachment"

  # instance_pool_id - (required) is a type of string
  instance_pool_id = null
  # instance_pool_load_balancer_attachment_id - (required) is a type of string
  instance_pool_load_balancer_attachment_id = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_pool_id" {
  description = "(required)"
  type        = string
}

variable "instance_pool_load_balancer_attachment_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_instance_pool_load_balancer_attachment" "this" {
  instance_pool_id                          = var.instance_pool_id
  instance_pool_load_balancer_attachment_id = var.instance_pool_load_balancer_attachment_id
}
```

[top](#index)

### Outputs

```terraform
output "backend_set_name" {
  description = "returns a string"
  value       = data.oci_core_instance_pool_load_balancer_attachment.this.backend_set_name
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_instance_pool_load_balancer_attachment.this.id
}

output "load_balancer_id" {
  description = "returns a string"
  value       = data.oci_core_instance_pool_load_balancer_attachment.this.load_balancer_id
}

output "port" {
  description = "returns a number"
  value       = data.oci_core_instance_pool_load_balancer_attachment.this.port
}

output "state" {
  description = "returns a string"
  value       = data.oci_core_instance_pool_load_balancer_attachment.this.state
}

output "vnic_selection" {
  description = "returns a string"
  value       = data.oci_core_instance_pool_load_balancer_attachment.this.vnic_selection
}

output "this" {
  value = oci_core_instance_pool_load_balancer_attachment.this
}
```

[top](#index)