### knife.rb

`knife.rb` in `.chef` folder:

```
current_dir = File.dirname(__FILE__)
log_level                :info
log_location             STDOUT
node_name                'node_name'
client_key               "#{current_dir}/USER.pem"
validation_client_name   'ORG_NAME-validator'
validation_key           "#{current_dir}/ORGANIZATION-validator.pem"
chef_server_url          'https://api.chef.io/organizations/ORG_NAME'
cache_type               'BasicFile'
cache_options( :path => "#{ENV['HOME']}/.chef/checksums" )
cookbook_path            ["#{current_dir}/../cookbooks"]
```

### Getting certs

```
> $ knife ssl fetch
[...]
Adding certificate for DigiCert_SHA2_Secure_Server_CA in /home/user/.chef/trusted_certs/DigiCert_SHA2_Secure_Server_CA.crt
```
