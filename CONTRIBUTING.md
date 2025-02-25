# Contributing to historical-bank-ruby

We're glad you want to make a contribution!

Fork this repository and send in a pull request when you're finished with your changes. Link any relevant issues in too.

Take note of the build status of your pull request, only builds that pass will be accepted. Please also keep to our conventions and style so we can keep this repository as clean as possible.


## Steps

1. Fork the repo
2. Grab dependencies: `bundle install`
3. Make sure specs are green: us e.g. `brew services start redis` the run Redis server and then `bundle exec rspec` to run the specs.
4. Make your changes
5. Run `rubocop -a`
6. Make sure specs are still green
7. Update `CHANGELOG.md` and `AUTHORS`
8. Issue a Pull Request and link any relevant issues


## Tips

Please make sure you read [README.md](README.md) before you start hacking so that you understand how the gem works :)

### Redis usage

The Redis cache that we use stores Hashes with keys formatted as `[namespace]:[base_currency]:[quote_currency]`.
These hashes contain ISO dates as keys with base currency rates as values.
For example, if `currency` is the Redis namespace we used in the config,
USD is the base currency, and we're looking for HUF rates, they can be found in the `currency:USD:HUF` key, and their format will be
```
{
  "2016-05-01": "0.272511002E3", # Rates are stored as BigDecimal Strings
  "2016-05-02": "0.270337998E3",
  "2016-05-03": "0.271477498E3"
}
```

The first key of this Hash translates to: "on May 1st 2016, 1 USD was equivalent to 272.511002 HUF".


### Memory caching

Apart from Redis, rates are also cached in the Bank's memory,
in `@rates`. `@rates` is a `Hash[iso_currency][iso_date]`
containing `BigDecimal` exchange rates of `iso_currency` on `iso_date`.
When they don't exist in memory, they are retrieved from the Store,
and when they don't exist in the Store, they are retrieved from the
Provider.


## Possible improvements

- Make Redis optional
- Add another provider (e.g. XE.com)
- Add another store (e.g. DynamoDB, MongoDB, Cassandra, Postgres, etc)


## License

By contributing your code, you agree to license your contribution under the terms of the APLv2: https://github.com/jeopard/historical-bank-ruby/blob/master/LICENSE

All files are released with the Apache 2.0 license.
