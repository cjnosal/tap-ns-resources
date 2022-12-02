# tap-ns-resources

1. update kapp-overlay for fields not in the grype package schema
2. update grype-airgap.lib-yaml to reference kapp-overlay and override values in the grype package schema
3. apply kapp-overlay.yaml to the tap-install namespace
4. Update tap-values to point at the grype-airgap overlay and provide CA cert
```
namespace_provisioner:
  additional_sources:
  - git:
      ref: origin/main
      subPath: grype-airgap/overlay
      url: https://github.com/xtreme-conor-nosal/tap-ns-resources.git
    path: _ytt_lib/customize
  #OR
  - git:
      ref: origin/main
      subPath: grype-airgap/replace
      url: https://github.com/xtreme-conor-nosal/tap-ns-resources.git
    path: _ytt_lib/grype-airgap
shared:
  ca_cert_data: |
    # PEM Certs
    # echo D | openssl s_client -connect registry.example:443 -showcerts 2>/dev/null|openssl x509 -outform PEM
```