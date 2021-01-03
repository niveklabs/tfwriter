# fastly

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "fastly" {
  version = "0.21.2"

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

- [fastly_user_v1](./r/fastly_user_v1.md)


[top](#index)

### Datasources


- [fastly_ip_ranges](./d/fastly_ip_ranges.md)

- [fastly_waf_rules](./d/fastly_waf_rules.md)


[top](#index)