# Changelog

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
