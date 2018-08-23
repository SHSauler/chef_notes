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

### Creating org on chef server

```
chef-server-ctl org-create cheftest "Cheftest Inc." -f /tmp/cheftest.key
```

### Creating user on chef server

```
chef-server-ctl user-create testot Testo Testenberger testot@example.local P@SSW0RD! -f testot.key
```


### Associate user with org

```
sudo chef-server-ctl org-user-add cheftest testot
```

### Upload cookbook

```
> $ knife cookbook upload learn_chef_apache2

Uploading learn_chef_apache2 [0.1.0]
Uploaded 1 cookbook.
```

Depends on `cookbook_path` set in `knife.rb`

```
cookbook_path            ["#{current_dir}/../cookbooks"]
```

### List cookbooks

```
> $ knife cookbook list

learn_chef_apache2   0.1.0
```


