# avi_sslkeyandcertificate

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_sslkeyandcertificate" {
  source = "./modules/avi/r/avi_sslkeyandcertificate"

  # certificate_base64 - (optional) is a type of bool
  certificate_base64 = null
  # certificate_management_profile_ref - (optional) is a type of string
  certificate_management_profile_ref = null
  # created_by - (optional) is a type of string
  created_by = null
  # enckey_base64 - (optional) is a type of string
  enckey_base64 = null
  # enckey_name - (optional) is a type of string
  enckey_name = null
  # format - (optional) is a type of string
  format = null
  # hardwaresecuritymodulegroup_ref - (optional) is a type of string
  hardwaresecuritymodulegroup_ref = null
  # key - (optional) is a type of string
  key = null
  # key_base64 - (optional) is a type of bool
  key_base64 = null
  # key_passphrase - (optional) is a type of string
  key_passphrase = null
  # name - (required) is a type of string
  name = null
  # status - (optional) is a type of string
  status = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # type - (optional) is a type of string
  type = null
  # uuid - (optional) is a type of string
  uuid = null

  ca_certs = [{
    ca_ref = null
    name   = null
  }]

  certificate = [{
    certificate                 = null
    certificate_signing_request = null
    chain_verified              = null
    days_until_expire           = null
    expiry_status               = null
    fingerprint                 = null
    issuer = [{
      common_name        = null
      country            = null
      distinguished_name = null
      email_address      = null
      locality           = null
      organization       = null
      organization_unit  = null
      state              = null
    }]
    key_params = [{
      algorithm = null
      ec_params = [{
        curve = null
      }]
      rsa_params = [{
        exponent = null
        key_size = null
      }]
    }]
    not_after           = null
    not_before          = null
    public_key          = null
    self_signed         = null
    serial_number       = null
    signature           = null
    signature_algorithm = null
    subject = [{
      common_name        = null
      country            = null
      distinguished_name = null
      email_address      = null
      locality           = null
      organization       = null
      organization_unit  = null
      state              = null
    }]
    subject_alt_names = []
    text              = null
    version           = null
  }]

  dynamic_params = [{
    is_dynamic   = null
    is_sensitive = null
    name         = null
    value        = null
  }]

  key_params = [{
    algorithm = null
    ec_params = [{
      curve = null
    }]
    rsa_params = [{
      exponent = null
      key_size = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "certificate_base64" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "certificate_management_profile_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "created_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enckey_base64" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enckey_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hardwaresecuritymodulegroup_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_base64" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "key_passphrase" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ca_certs" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ca_ref = string
      name   = string
    }
  ))
  default = []
}

variable "certificate" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      certificate                 = string
      certificate_signing_request = string
      chain_verified              = bool
      days_until_expire           = number
      expiry_status               = string
      fingerprint                 = string
      issuer = set(object(
        {
          common_name        = string
          country            = string
          distinguished_name = string
          email_address      = string
          locality           = string
          organization       = string
          organization_unit  = string
          state              = string
        }
      ))
      key_params = set(object(
        {
          algorithm = string
          ec_params = set(object(
            {
              curve = string
            }
          ))
          rsa_params = set(object(
            {
              exponent = number
              key_size = string
            }
          ))
        }
      ))
      not_after           = string
      not_before          = string
      public_key          = string
      self_signed         = bool
      serial_number       = string
      signature           = string
      signature_algorithm = string
      subject = set(object(
        {
          common_name        = string
          country            = string
          distinguished_name = string
          email_address      = string
          locality           = string
          organization       = string
          organization_unit  = string
          state              = string
        }
      ))
      subject_alt_names = list(string)
      text              = string
      version           = string
    }
  ))
}

variable "dynamic_params" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      is_dynamic   = bool
      is_sensitive = bool
      name         = string
      value        = string
    }
  ))
  default = []
}

variable "key_params" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      algorithm = string
      ec_params = set(object(
        {
          curve = string
        }
      ))
      rsa_params = set(object(
        {
          exponent = number
          key_size = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_sslkeyandcertificate" "this" {
  # certificate_base64 - (optional) is a type of bool
  certificate_base64 = var.certificate_base64
  # certificate_management_profile_ref - (optional) is a type of string
  certificate_management_profile_ref = var.certificate_management_profile_ref
  # created_by - (optional) is a type of string
  created_by = var.created_by
  # enckey_base64 - (optional) is a type of string
  enckey_base64 = var.enckey_base64
  # enckey_name - (optional) is a type of string
  enckey_name = var.enckey_name
  # format - (optional) is a type of string
  format = var.format
  # hardwaresecuritymodulegroup_ref - (optional) is a type of string
  hardwaresecuritymodulegroup_ref = var.hardwaresecuritymodulegroup_ref
  # key - (optional) is a type of string
  key = var.key
  # key_base64 - (optional) is a type of bool
  key_base64 = var.key_base64
  # key_passphrase - (optional) is a type of string
  key_passphrase = var.key_passphrase
  # name - (required) is a type of string
  name = var.name
  # status - (optional) is a type of string
  status = var.status
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # type - (optional) is a type of string
  type = var.type
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "ca_certs" {
    for_each = var.ca_certs
    content {
      # ca_ref - (optional) is a type of string
      ca_ref = ca_certs.value["ca_ref"]
      # name - (optional) is a type of string
      name = ca_certs.value["name"]
    }
  }

  dynamic "certificate" {
    for_each = var.certificate
    content {
      # certificate - (optional) is a type of string
      certificate = certificate.value["certificate"]
      # certificate_signing_request - (optional) is a type of string
      certificate_signing_request = certificate.value["certificate_signing_request"]
      # chain_verified - (optional) is a type of bool
      chain_verified = certificate.value["chain_verified"]
      # days_until_expire - (optional) is a type of number
      days_until_expire = certificate.value["days_until_expire"]
      # expiry_status - (optional) is a type of string
      expiry_status = certificate.value["expiry_status"]
      # fingerprint - (optional) is a type of string
      fingerprint = certificate.value["fingerprint"]
      # not_after - (optional) is a type of string
      not_after = certificate.value["not_after"]
      # not_before - (optional) is a type of string
      not_before = certificate.value["not_before"]
      # public_key - (optional) is a type of string
      public_key = certificate.value["public_key"]
      # self_signed - (optional) is a type of bool
      self_signed = certificate.value["self_signed"]
      # serial_number - (optional) is a type of string
      serial_number = certificate.value["serial_number"]
      # signature - (optional) is a type of string
      signature = certificate.value["signature"]
      # signature_algorithm - (optional) is a type of string
      signature_algorithm = certificate.value["signature_algorithm"]
      # subject_alt_names - (optional) is a type of list of string
      subject_alt_names = certificate.value["subject_alt_names"]
      # text - (optional) is a type of string
      text = certificate.value["text"]
      # version - (optional) is a type of string
      version = certificate.value["version"]

      dynamic "issuer" {
        for_each = certificate.value.issuer
        content {
          # common_name - (optional) is a type of string
          common_name = issuer.value["common_name"]
          # country - (optional) is a type of string
          country = issuer.value["country"]
          # distinguished_name - (optional) is a type of string
          distinguished_name = issuer.value["distinguished_name"]
          # email_address - (optional) is a type of string
          email_address = issuer.value["email_address"]
          # locality - (optional) is a type of string
          locality = issuer.value["locality"]
          # organization - (optional) is a type of string
          organization = issuer.value["organization"]
          # organization_unit - (optional) is a type of string
          organization_unit = issuer.value["organization_unit"]
          # state - (optional) is a type of string
          state = issuer.value["state"]
        }
      }

      dynamic "key_params" {
        for_each = certificate.value.key_params
        content {
          # algorithm - (required) is a type of string
          algorithm = key_params.value["algorithm"]

          dynamic "ec_params" {
            for_each = key_params.value.ec_params
            content {
              # curve - (optional) is a type of string
              curve = ec_params.value["curve"]
            }
          }

          dynamic "rsa_params" {
            for_each = key_params.value.rsa_params
            content {
              # exponent - (optional) is a type of number
              exponent = rsa_params.value["exponent"]
              # key_size - (optional) is a type of string
              key_size = rsa_params.value["key_size"]
            }
          }

        }
      }

      dynamic "subject" {
        for_each = certificate.value.subject
        content {
          # common_name - (optional) is a type of string
          common_name = subject.value["common_name"]
          # country - (optional) is a type of string
          country = subject.value["country"]
          # distinguished_name - (optional) is a type of string
          distinguished_name = subject.value["distinguished_name"]
          # email_address - (optional) is a type of string
          email_address = subject.value["email_address"]
          # locality - (optional) is a type of string
          locality = subject.value["locality"]
          # organization - (optional) is a type of string
          organization = subject.value["organization"]
          # organization_unit - (optional) is a type of string
          organization_unit = subject.value["organization_unit"]
          # state - (optional) is a type of string
          state = subject.value["state"]
        }
      }

    }
  }

  dynamic "dynamic_params" {
    for_each = var.dynamic_params
    content {
      # is_dynamic - (optional) is a type of bool
      is_dynamic = dynamic_params.value["is_dynamic"]
      # is_sensitive - (optional) is a type of bool
      is_sensitive = dynamic_params.value["is_sensitive"]
      # name - (required) is a type of string
      name = dynamic_params.value["name"]
      # value - (optional) is a type of string
      value = dynamic_params.value["value"]
    }
  }

  dynamic "key_params" {
    for_each = var.key_params
    content {
      # algorithm - (required) is a type of string
      algorithm = key_params.value["algorithm"]

      dynamic "ec_params" {
        for_each = key_params.value.ec_params
        content {
          # curve - (optional) is a type of string
          curve = ec_params.value["curve"]
        }
      }

      dynamic "rsa_params" {
        for_each = key_params.value.rsa_params
        content {
          # exponent - (optional) is a type of number
          exponent = rsa_params.value["exponent"]
          # key_size - (optional) is a type of string
          key_size = rsa_params.value["key_size"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "certificate_management_profile_ref" {
  description = "returns a string"
  value       = avi_sslkeyandcertificate.this.certificate_management_profile_ref
}

output "created_by" {
  description = "returns a string"
  value       = avi_sslkeyandcertificate.this.created_by
}

output "enckey_base64" {
  description = "returns a string"
  value       = avi_sslkeyandcertificate.this.enckey_base64
}

output "enckey_name" {
  description = "returns a string"
  value       = avi_sslkeyandcertificate.this.enckey_name
}

output "hardwaresecuritymodulegroup_ref" {
  description = "returns a string"
  value       = avi_sslkeyandcertificate.this.hardwaresecuritymodulegroup_ref
}

output "id" {
  description = "returns a string"
  value       = avi_sslkeyandcertificate.this.id
}

output "key" {
  description = "returns a string"
  value       = avi_sslkeyandcertificate.this.key
}

output "key_passphrase" {
  description = "returns a string"
  value       = avi_sslkeyandcertificate.this.key_passphrase
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_sslkeyandcertificate.this.tenant_ref
}

output "type" {
  description = "returns a string"
  value       = avi_sslkeyandcertificate.this.type
}

output "uuid" {
  description = "returns a string"
  value       = avi_sslkeyandcertificate.this.uuid
}

output "this" {
  value = avi_sslkeyandcertificate.this
}
```

[top](#index)