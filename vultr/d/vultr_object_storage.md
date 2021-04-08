# vultr_object_storage

[back](../vultr.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vultr = ">= 2.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vultr_object_storage" {
  source = "./modules/vultr/d/vultr_object_storage"


  filter = [{
    name   = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "vultr_object_storage" "this" {

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # values - (required) is a type of list of string
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cluster_id" {
  description = "returns a number"
  value       = data.vultr_object_storage.this.cluster_id
}

output "date_created" {
  description = "returns a string"
  value       = data.vultr_object_storage.this.date_created
}

output "id" {
  description = "returns a string"
  value       = data.vultr_object_storage.this.id
}

output "label" {
  description = "returns a string"
  value       = data.vultr_object_storage.this.label
}

output "location" {
  description = "returns a string"
  value       = data.vultr_object_storage.this.location
}

output "region" {
  description = "returns a string"
  value       = data.vultr_object_storage.this.region
}

output "s3_access_key" {
  description = "returns a string"
  value       = data.vultr_object_storage.this.s3_access_key
  sensitive   = true
}

output "s3_hostname" {
  description = "returns a string"
  value       = data.vultr_object_storage.this.s3_hostname
}

output "s3_secret_key" {
  description = "returns a string"
  value       = data.vultr_object_storage.this.s3_secret_key
  sensitive   = true
}

output "status" {
  description = "returns a string"
  value       = data.vultr_object_storage.this.status
}

output "this" {
  value = vultr_object_storage.this
}
```

[top](#index)