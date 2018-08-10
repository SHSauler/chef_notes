## Notes on ruby behavior

Ruby perculiarities.


### Symbols

`:example` is a symbol. It's used in Ruby as key in hashes. Symbols are immutable.

#### Methods on symbols

```
:test.upcase  
=> :TEST

:test.downcase  
=> :test

:test.capitalize  
=> :Test  
```

### Strings

#### String concat

```
full_path = "#{directory}\\#{filename}"
```

#### Convert to string

```
:start.to_s
```

#### Make string immutable

```
hello = 'hello'
=> "hello"
 hello.freeze
=> "hello"
hello << "test"

FrozenError (can't modify frozen String)
```

### Arrays

```
array.first
array.last
array << newitem

array_properly_escaped = %w[ element1 element2 element3 ]
```

#### Operations over arrays

```
array.each do |action_name|
  Chef::Log.info action_name
end
```

### Hashes

Setting like Python dicts, acessing with preceding `:`

```
hash_name = {
  entry1: 'string',
  entry2: 'string2'
}

Chef::Log.info hash_name[:entry1]
```



