# oci_objectstorage_preauthrequest

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_objectstorage_preauthrequest" {
  source = "./modules/oci/d/oci_objectstorage_preauthrequest"

  # bucket - (required) is a type of string
  bucket = null
  # namespace - (required) is a type of string
  namespace = null
  # par_id - (required) is a type of string
  par_id = null
}
```

[top](#index)

### Variables

```terraform
variable "bucket" {
  description = "(required)"
  type        = string
}

variable "namespace" {
  description = "(required)"
  type        = string
}

variable "par_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_objectstorage_preauthrequest" "this" {
  bucket    = var.bucket
  namespace = var.namespace
  par_id    = var.par_id
}
```

[top](#index)

### Outputs

```terraform
output "access_type" {
  description = "returns a string"
  value       = data.oci_objectstorage_preauthrequest.this.access_type
}

output "access_uri" {
  description = "returns a string"
  value       = data.oci_objectstorage_preauthrequest.this.access_uri
}

output "id" {
  description = "returns a string"
  value       = data.oci_objectstorage_preauthrequest.this.id
}

output "name" {
  description = "returns a string"
  value       = data.oci_objectstorage_preauthrequest.this.name
}

output "object" {
  description = "returns a string"
  value       = data.oci_objectstorage_preauthrequest.this.object
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_objectstorage_preauthrequest.this.time_created
}

output "time_expires" {
  description = "returns a string"
  value       = data.oci_objectstorage_preauthrequest.this.time_expires
}

output "this" {
  value = oci_objectstorage_preauthrequest.this
}
```

[top](#index)