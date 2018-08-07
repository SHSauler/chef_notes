### Create cookbook

```
$ chef generate cookbook cookbook_name
```

### Add template

```
$ chef generate template cookbook_name index.html

$ tree
.
├── Berksfile
├── chefignore
├── LICENSE
├── metadata.rb
├── README.md
├── recipes
│   └── default.rb
├── spec
│   ├── spec_helper.rb
│   └── unit
│       └── recipes
│           └── default_spec.rb
├── templates
│   └── index.html.erb
└── test
    └── integration
        └── default
            └── default_test.rb
```

### Run cookbook

```
sudo chef-client --local-mode --runlist 'recipe[name_of_recipe]'
```
