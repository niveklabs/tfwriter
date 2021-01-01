# google_iap_client

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_iap_client" {
  source = "./modules/google/r/google_iap_client"

  # brand - (required) is a type of string
  brand = null
  # display_name - (required) is a type of string
  display_name = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "brand" {
  description = "(required) - Identifier of the brand to which this client\nis attached to. The format is\n'projects/{project_number}/brands/{brand_id}/identityAwareProxyClients/{client_id}'."
  type        = string
}

variable "display_name" {
  description = "(required) - Human-friendly name given to the OAuth client."
  type        = string
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "google_iap_client" "this" {
  brand        = var.brand
  display_name = var.display_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "client_id" {
  description = "returns a string"
  value       = google_iap_client.this.client_id
}

output "id" {
  description = "returns a string"
  value       = google_iap_client.this.id
}

output "secret" {
  description = "returns a string"
  value       = google_iap_client.this.secret
  sensitive   = true
}

output "this" {
  value = google_iap_client.this
}
```

[top](#index)