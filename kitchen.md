### Kitchen lifecycle

```
kitchen list
kitchen create
kitchen converge
kitchen exec -c 'command'
kitchen destroy
```

### Kitchen with vagrant

```
---
driver:
  name: vagrant

provisioner:
  name: chef_zero
  # You may wish to disable always updating cookbooks in CI or other testing environments.
  # For example:
  #   always_update_cookbooks: <%= !ENV['CI'] %>
  always_update_cookbooks: false

verifier:
  name: inspec

platforms:
  - name: ubuntu-18.04

suites:
  - name: default
    run_list:
      - recipe[$nameofcookbook::default]
    verifier:
      inspec_tests:
        - test/smoke/default
    attributes:
    ```


### Testing tools

```
# foodcritic .
Checking 5 files
[...]
# cookstyle . 
Inspecting 8 files
[...]
```
