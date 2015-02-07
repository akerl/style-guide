Ruby Style Guide
===========

Here are some guidelines I try to follow in my Ruby projects. These are all in addition to [The Ruby Style Guide](https://github.com/bbatsov/ruby-style-guide), as enforced by [rubocop](https://github.com/bbatsov/rubocop).

## Naming

### Option hashes

When naming hashes used to pass around options or parameters, use the following convention:

#### The hash portion of a method's input is "params"

```
class Example
  def initialize(params = {})
  end
end
```

#### Options stored on the instance are "@options"

```
class Example
  def initialize(params = {})
    @options = parse(params)
  end
end
```

#### If you're storing the direct results of a config file, use "@config"

```
class Example
  def initialize(params = {})
    @config = load_config(params[:config_file])
  end
end
```

Where possible, you should be sanity-checking config file data. Sanitized config file data should use `@options`, not `@config`

