# avi_pkiprofile

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
module "avi_pkiprofile" {
  source = "./modules/avi/r/avi_pkiprofile"

  # created_by - (optional) is a type of string
  created_by = null
  # crl_check - (optional) is a type of bool
  crl_check = null
  # ignore_peer_chain - (optional) is a type of bool
  ignore_peer_chain = null
  # is_federated - (optional) is a type of bool
  is_federated = null
  # name - (required) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
  # validate_only_leaf_crl - (optional) is a type of bool
  validate_only_leaf_crl = null

  ca_certs = [{
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

  crls = [{
    body               = null
    common_name        = null
    distinguished_name = null
    etag               = null
    fingerprint        = null
    last_refreshed     = null
    last_update        = null
    next_update        = null
    server_url         = null
    text               = null
    update_interval    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "created_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "crl_check" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ignore_peer_chain" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_federated" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "validate_only_leaf_crl" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ca_certs" {
  description = "nested block: NestingList, min items: 0, max items: 0"
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
  default = []
}

variable "crls" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      body               = string
      common_name        = string
      distinguished_name = string
      etag               = string
      fingerprint        = string
      last_refreshed     = string
      last_update        = string
      next_update        = string
      server_url         = string
      text               = string
      update_interval    = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_pkiprofile" "this" {
  # created_by - (optional) is a type of string
  created_by = var.created_by
  # crl_check - (optional) is a type of bool
  crl_check = var.crl_check
  # ignore_peer_chain - (optional) is a type of bool
  ignore_peer_chain = var.ignore_peer_chain
  # is_federated - (optional) is a type of bool
  is_federated = var.is_federated
  # name - (required) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid
  # validate_only_leaf_crl - (optional) is a type of bool
  validate_only_leaf_crl = var.validate_only_leaf_crl

  dynamic "ca_certs" {
    for_each = var.ca_certs
    content {
      # certificate - (optional) is a type of string
      certificate = ca_certs.value["certificate"]
      # certificate_signing_request - (optional) is a type of string
      certificate_signing_request = ca_certs.value["certificate_signing_request"]
      # chain_verified - (optional) is a type of bool
      chain_verified = ca_certs.value["chain_verified"]
      # days_until_expire - (optional) is a type of number
      days_until_expire = ca_certs.value["days_until_expire"]
      # expiry_status - (optional) is a type of string
      expiry_status = ca_certs.value["expiry_status"]
      # fingerprint - (optional) is a type of string
      fingerprint = ca_certs.value["fingerprint"]
      # not_after - (optional) is a type of string
      not_after = ca_certs.value["not_after"]
      # not_before - (optional) is a type of string
      not_before = ca_certs.value["not_before"]
      # public_key - (optional) is a type of string
      public_key = ca_certs.value["public_key"]
      # self_signed - (optional) is a type of bool
      self_signed = ca_certs.value["self_signed"]
      # serial_number - (optional) is a type of string
      serial_number = ca_certs.value["serial_number"]
      # signature - (optional) is a type of string
      signature = ca_certs.value["signature"]
      # signature_algorithm - (optional) is a type of string
      signature_algorithm = ca_certs.value["signature_algorithm"]
      # subject_alt_names - (optional) is a type of list of string
      subject_alt_names = ca_certs.value["subject_alt_names"]
      # text - (optional) is a type of string
      text = ca_certs.value["text"]
      # version - (optional) is a type of string
      version = ca_certs.value["version"]

      dynamic "issuer" {
        for_each = ca_certs.value.issuer
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
        for_each = ca_certs.value.key_params
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
        for_each = ca_certs.value.subject
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

  dynamic "crls" {
    for_each = var.crls
    content {
      # body - (optional) is a type of string
      body = crls.value["body"]
      # common_name - (optional) is a type of string
      common_name = crls.value["common_name"]
      # distinguished_name - (optional) is a type of string
      distinguished_name = crls.value["distinguished_name"]
      # etag - (optional) is a type of string
      etag = crls.value["etag"]
      # fingerprint - (optional) is a type of string
      fingerprint = crls.value["fingerprint"]
      # last_refreshed - (optional) is a type of string
      last_refreshed = crls.value["last_refreshed"]
      # last_update - (optional) is a type of string
      last_update = crls.value["last_update"]
      # next_update - (optional) is a type of string
      next_update = crls.value["next_update"]
      # server_url - (optional) is a type of string
      server_url = crls.value["server_url"]
      # text - (optional) is a type of string
      text = crls.value["text"]
      # update_interval - (optional) is a type of number
      update_interval = crls.value["update_interval"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_by" {
  description = "returns a string"
  value       = avi_pkiprofile.this.created_by
}

output "id" {
  description = "returns a string"
  value       = avi_pkiprofile.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_pkiprofile.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_pkiprofile.this.uuid
}

output "this" {
  value = avi_pkiprofile.this
}
```

[top](#index)