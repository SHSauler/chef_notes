## Kitchen

### Kitchen lifecycle

```
kitchen list
kitchen create
kitchen converge
kitchen exec -c 'command'
kitchen destroy
```

### Kitchen test

`kitchen test` command performs a complete Test Kitchen run, namely:

```
kitchen destroy
kitchen create
kitchen converge
kitchen verify
kitchen destroy
```

Afterwards `kitchen test` can determine whether inspec tests passed.

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

## Testing tools

### Foodcritic

Metadata linting tool

```
foodcritic .
```

### Cookstyle

Ruby static code analyzer

```
cookstyle . 
```

To autocorrect violations

```
cookstyle -a .
```

## Testing specs

```
chef exec rspec .
```

## Verification of inspec

In the kitchen config

```
verifier:
  name: inspec
```

Running the verification

```
kitchen verify
```
