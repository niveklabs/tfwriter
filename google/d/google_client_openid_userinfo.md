# google_client_openid_userinfo

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
module "google_client_openid_userinfo" {
  source = "./modules/google/d/google_client_openid_userinfo"

}
```

[top](#index)

### Variables

```hcl
```

[top](#index)

### Datasource

```hcl
data "google_client_openid_userinfo" "this" {
}
```

[top](#index)

### Outputs

```hcl
output "email" {
  description = "returns a string"
  value       = data.google_client_openid_userinfo.this.email
}

output "id" {
  description = "returns a string"
  value       = data.google_client_openid_userinfo.this.id
}

output "this" {
  value = google_client_openid_userinfo.this
}
```

[top](#index)