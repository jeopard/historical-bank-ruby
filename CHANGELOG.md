# Changelog

## 0.1.9

- Add support for `money` gem version 7.x (while retaining 6.x compatibility). Note: `money` 7.0 changes the default rounding mode from `ROUND_HALF_EVEN` to `ROUND_HALF_UP`. If upgrading to `money` 7.x, set `Money.rounding_mode = BigDecimal::ROUND_HALF_EVEN` in your initializer to preserve the previous behavior.

## 0.1.8

- Add optional `redis_params` configuration to pass extra parameters to `Redis.new` (e.g. SSL options). Thank you @cattekin!
- Drop support for EOL Ruby versions; minimum Ruby version is now 3.1.0
- Update `redis` gem dependency from `['>=3.3', '~> 4.0']` to `['>=4.0', '~> 5.0']` and fix breaking changes
- Update development dependencies (`rubocop`, `webmock`, `rack-test`, `faker`)
- Code style improvements via RuboCop

## 0.1.7

- Fix bug with Ruby memory cache not used. Thank you @stanley90!!

## 0.1.6

- Update how Redis pipeline command is made. The old way will be removed in Redis 5.0.0

## 0.1.5

- Use `Dir` instead of `FileList` in the gemspec to resolve [external dependency error](https://github.com/rubygems/rubygems/issues/3313)

## 0.1.4

- Update Travis config and docs

## 0.1.3

- Support `redis` gem versions '>=3.3', '< 4.1' (#3)

## 0.1.0

- Added basic functionality and documentation.

## 0.1.1

- Added support for FREE and DEVELOPER OpenExchangeRates accounts. Downside when using these accounts is that OER rates are fetched for a single day at a time (as opposed to a whole month for more advanced plans).
- Developers have to specify `oer_account_type` during configuration.

## 0.1.2

- Updated `rubocop` gem needed for development due to low-severity security issue with version 0.46
