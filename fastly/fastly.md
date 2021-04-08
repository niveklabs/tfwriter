---
layout: resource
title: fastly
type: provider
resource: fastly
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "fastly" {
  version = "0.28.1"

  # api_key - (optional) is a type of string
  api_key = null
  # base_url - (optional) is a type of string
  base_url = null
}
```

[top](#index)

### Resources


- [fastly_service_acl_entries_v1](./r/fastly_service_acl_entries_v1.md)

- [fastly_service_compute](./r/fastly_service_compute.md)

- [fastly_service_dictionary_items_v1](./r/fastly_service_dictionary_items_v1.md)

- [fastly_service_dynamic_snippet_content_v1](./r/fastly_service_dynamic_snippet_content_v1.md)

- [fastly_service_v1](./r/fastly_service_v1.md)

- [fastly_service_waf_configuration](./r/fastly_service_waf_configuration.md)

- [fastly_tls_activation](./r/fastly_tls_activation.md)

- [fastly_tls_certificate](./r/fastly_tls_certificate.md)

- [fastly_tls_platform_certificate](./r/fastly_tls_platform_certificate.md)

- [fastly_tls_private_key](./r/fastly_tls_private_key.md)

- [fastly_tls_subscription](./r/fastly_tls_subscription.md)

- [fastly_tls_subscription_validation](./r/fastly_tls_subscription_validation.md)

- [fastly_user_v1](./r/fastly_user_v1.md)


[top](#index)

### Datasources


- [fastly_ip_ranges](./d/fastly_ip_ranges.md)

- [fastly_tls_activation](./d/fastly_tls_activation.md)

- [fastly_tls_activation_ids](./d/fastly_tls_activation_ids.md)

- [fastly_tls_certificate](./d/fastly_tls_certificate.md)

- [fastly_tls_certificate_ids](./d/fastly_tls_certificate_ids.md)

- [fastly_tls_configuration](./d/fastly_tls_configuration.md)

- [fastly_tls_configuration_ids](./d/fastly_tls_configuration_ids.md)

- [fastly_tls_domain](./d/fastly_tls_domain.md)

- [fastly_tls_platform_certificate](./d/fastly_tls_platform_certificate.md)

- [fastly_tls_platform_certificate_ids](./d/fastly_tls_platform_certificate_ids.md)

- [fastly_tls_private_key](./d/fastly_tls_private_key.md)

- [fastly_tls_private_key_ids](./d/fastly_tls_private_key_ids.md)

- [fastly_tls_subscription](./d/fastly_tls_subscription.md)

- [fastly_tls_subscription_ids](./d/fastly_tls_subscription_ids.md)

- [fastly_waf_rules](./d/fastly_waf_rules.md)


[top](#index)