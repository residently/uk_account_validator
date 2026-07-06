UkAccountValidator
==================

Fork of [ball-hayden/uk_account_validator](https://github.com/ball-hayden/uk_account_validator) maintained by Residently to keep the modulus checking data up to date.

This gem validates UK account numbers against their sort codes in accordance with VocaLink's modulus checking specification, which can be downloaded from [here](https://www.vocalink.com/tools/modulus-checking/).

Note that this gem ensures the sort code and account number are valid, not that they exist.

The resource text files `valacdos.txt` and `scsubtab.txt` are produced and released by VocaLink.

Requires Ruby > 2.0.0

## Data sources

- `valacdos.txt` (modulus weight table): https://www.vocalink.com/media/jsjlwqy5/valacdos.txt
- `scsubtab.txt` (sort code substitution table): https://www.vocalink.com/media/tedlwtxz/scsubtab.txt

VocaLink publishes updates roughly quarterly. Last updated: 2026-07-06.

## Usage

```ruby
UkAccountValidator::Validator.new(sort_code, account_number).valid?
```

or

```ruby
validator = UkAccountValidator::Validator.new
validator.account_number = account_number
validator.sort_code      = sort_code
validator.valid?
```

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'uk_account_validator', github: 'residently/uk_account_validator'
```

And then execute:

```
$ bundle
```

## Updating the data

1. Download the latest `valacdos.txt` from the VocaLink link above
2. Replace `data/valacdos.txt`
3. Commit and push
