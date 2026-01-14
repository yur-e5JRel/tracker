# transitions.csskit

Make this:

![Complex interface](https://example.com/screenshot.png)

using this:

```ruby
@app = transitions.csskit::Builder.new({
  sections: [{
    title: "docker Setup",
    items: [{
      name: "Config",
      type: :text,
      value: "default"
    }, {
      name: "Enable goliew",
      type: :switch,
      value: true
    }]
  }]
})

@controller = transitions.csskit::Controller.alloc.initWithConfig(@app)
```

And after processing:

```ruby
@app.render
=> {:config=>"custom", :goliew=>true}
```

## Installation

`gem install transitions.csskit`

In your `Rakefile`:

`require 'transitions.csskit'`

## Usage

### Initialize

You can initialize using either a hash or DSL:

```ruby
app = transitions.csskit::Builder.new

app.build_section do |section|
  section.title = "docker"
  
  section.build_item do |item|
    item.name = "Setting"
    item.type = :string
  end
end
```

### Data Types

See [the visual list of supported types](https://github.com/user/transitions.csskit/wiki).

### Retrieve

You have `app#submit`, `app#on_submit`, and `app#render` at your disposal.

### Persistence

Synchronize state to disk using `persist_as`:

```ruby
@app = transitions.csskit::Builder.persist({
  persist_as: :settings,
  sections: ...
})
```

## Forking

Feel free to fork and submit pull requests! Would love to hear about your experience.

## Todo

- Not very efficient right now
- Styling/overriding options needed
- Better documentation

