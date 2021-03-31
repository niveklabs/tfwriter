# google_iap_client

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_iap_client" {
  source = "./modules/google/d/google_iap_client"

  # brand - (required) is a type of string
  brand = null
  # client_id - (required) is a type of string
  client_id = null
}
```

[top](#index)

### Variables

```terraform
variable "brand" {
  description = "(required) - Identifier of the brand to which this client\nis attached to. The format is\n'projects/{project_number}/brands/{brand_id}/identityAwareProxyClients/{client_id}'."
  type        = string
}

variable "client_id" {
  description = "(required) - Output only. Unique identifier of the OAuth client."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "google_iap_client" "this" {
  brand     = var.brand
  client_id = var.client_id
}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = data.google_iap_client.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.google_iap_client.this.id
}

output "secret" {
  description = "returns a string"
  value       = data.google_iap_client.this.secret
}

output "this" {
  value = google_iap_client.this
}
```

[top](#index)