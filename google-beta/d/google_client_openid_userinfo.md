# google_client_openid_userinfo

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_client_openid_userinfo" {
  source = "./modules/google-beta/d/google_client_openid_userinfo"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "google_client_openid_userinfo" "this" {
}
```

[top](#index)

### Outputs

```terraform
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