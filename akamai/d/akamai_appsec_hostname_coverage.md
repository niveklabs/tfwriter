# akamai_appsec_hostname_coverage

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_appsec_hostname_coverage" {
  source = "./modules/akamai/d/akamai_appsec_hostname_coverage"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "akamai_appsec_hostname_coverage" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.akamai_appsec_hostname_coverage.this.id
}

output "json" {
  description = "returns a string"
  value       = data.akamai_appsec_hostname_coverage.this.json
}

output "output_text" {
  description = "returns a string"
  value       = data.akamai_appsec_hostname_coverage.this.output_text
}

output "this" {
  value = akamai_appsec_hostname_coverage.this
}
```

[top](#index)