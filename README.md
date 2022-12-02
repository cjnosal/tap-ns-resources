# tap-ns-resources

```
namespace_provisioner:
  additional_sources:
  - git:
      ref: origin/main
      subPath: grype-airgap
      url: https://github.com/xtreme-conor-nosal/tap-ns-resources.git
    path: _ytt_lib/customize
grype:
  db:
    dbUpdateUrl: example.com/listing.json
shared:
  ca_cert_data: |
    # PEM Certs
    # echo D | openssl s_client -connect registry.example:443 -showcerts 2>/dev/null|openssl x509 -outform PEM
```