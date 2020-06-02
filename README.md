# Jekyll::WebMonetization

A Jekyll plugin to add [Web Monetization API](https://webmonetization.org/) payment pointers to your site.

## Web Monetization

A JavaScript browser API which allows the creation of a payment stream from the user agent to the website.

[Find out more about Web Monetization](https://webmonetization.org/).

### Payment pointer

To use this plugin and receive payments from Web Monetization you will need a payment pointer. A payment pointer is an address at which you can receive streaming payments from the Web Monetization API. You can set up a payment pointer by creating a digital wallet with [one of the providers listed on the Web Monetization API site](https://webmonetization.org/docs/ilp-wallets).

You can read more about [payment pointers](https://paymentpointers.org/) and [receiving money from Web Monetization](https://webmonetization.org/docs/receiving) in the relevant documentation.

## Installation

Add the gem to the `:jekyll_plugins` group in your Jekyll site's Gemfile:

```ruby
group :jekyll_plugins do
  gem 'jekyll-web_monetization'
end
```

Execute:

```bash
  $ bundle install
```

Then in your site's `_config.yml` add the plugin to the plugins list:

```yml
plugins:
  - jekyll/web_monetization
```

## Usage

Once you have a payment pointer, add it to your site settings in `_config.yml`:

```yml
payment_pointer: $securewallet.example/~alice
```

Also, add the `web_monetization` liquid tag to the `<head>` of your layout.

```html
<head>
  <!-- other tags in the head -->
  {% web_monetization %}
</head>
```

The site-wide payment pointer will be added to all pages on which you use the liquid tag.

If you have multiple authors, you can set a payment pointer per post or page in the YAML front matter. This will over-ride the site-wide payment pointer for that page.

```yml
---
payment_pointer: $securewallet.example/~bob
---
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake spec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/philnash/jekyll-web_monetization. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [code of conduct](./CODE_OF_CONDUCT.md).

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

## Code of Conduct

Everyone interacting in the Jekyll::Web::Monetization project's codebases, issue trackers, chat rooms and mailing lists is expected to follow the [code of conduct](./CODE_OF_CONDUCT.md).
