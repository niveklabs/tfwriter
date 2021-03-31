# github_ip_ranges

[back](../github.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    github = ">= 4.6.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "github_ip_ranges" {
  source = "./modules/github/d/github_ip_ranges"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "github_ip_ranges" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "git" {
  description = "returns a list of string"
  value       = data.github_ip_ranges.this.git
}

output "hooks" {
  description = "returns a list of string"
  value       = data.github_ip_ranges.this.hooks
}

output "id" {
  description = "returns a string"
  value       = data.github_ip_ranges.this.id
}

output "importer" {
  description = "returns a list of string"
  value       = data.github_ip_ranges.this.importer
}

output "pages" {
  description = "returns a list of string"
  value       = data.github_ip_ranges.this.pages
}

output "this" {
  value = github_ip_ranges.this
}
```

[top](#index)