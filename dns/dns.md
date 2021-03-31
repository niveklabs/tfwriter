# dns

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "dns" {
  version = "3.1.0"

  # NestingList
  update {
    # key_algorithm - (optional) is a type of string
    key_algorithm = null
    # key_name - (optional) is a type of string
    key_name = null
    # key_secret - (optional) is a type of string
    key_secret = null
    # port - (optional) is a type of number
    port = null
    # retries - (optional) is a type of number
    retries = null
    # server - (required) is a type of string
    server = null
    # timeout - (optional) is a type of string
    timeout = null
    # transport - (optional) is a type of string
    transport = null

    # NestingList
    gssapi {
      # keytab - (optional) is a type of string
      keytab = null
      # password - (optional) is a type of string
      password = null
      # realm - (required) is a type of string
      realm = null
      # username - (optional) is a type of string
      username = null
    }
  }
}
```

[top](#index)

### Resources


- [dns_a_record_set](./r/dns_a_record_set.md)

- [dns_aaaa_record_set](./r/dns_aaaa_record_set.md)

- [dns_cname_record](./r/dns_cname_record.md)

- [dns_mx_record_set](./r/dns_mx_record_set.md)

- [dns_ns_record_set](./r/dns_ns_record_set.md)

- [dns_ptr_record](./r/dns_ptr_record.md)

- [dns_srv_record_set](./r/dns_srv_record_set.md)

- [dns_txt_record_set](./r/dns_txt_record_set.md)


[top](#index)

### Datasources


- [dns_a_record_set](./d/dns_a_record_set.md)

- [dns_aaaa_record_set](./d/dns_aaaa_record_set.md)

- [dns_cname_record_set](./d/dns_cname_record_set.md)

- [dns_mx_record_set](./d/dns_mx_record_set.md)

- [dns_ns_record_set](./d/dns_ns_record_set.md)

- [dns_ptr_record_set](./d/dns_ptr_record_set.md)

- [dns_srv_record_set](./d/dns_srv_record_set.md)

- [dns_txt_record_set](./d/dns_txt_record_set.md)


[top](#index)