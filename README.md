OFX Parser
=================

## This is a fork of [oriatec/ofxparser](https://github.com/oriatec/ofxparser)

Added support PHP 8
Remove Investment Support
Fix depreciation and refactor

--------------------

OFX Parser is a PHP library designed to parse an OFX file downloaded from a financial institution into simple PHP objects.

It supports multiple Bank Accounts, the required "Sign On" response, and recognises OFX timestamps.

## Installation

Simply require the package using [Composer](https://getcomposer.org/):

```bash
$ composer require onewebbr/ofxparser
```

## Usage

You can access the nodes in your OFX file as follows:

```php
$ofxParser = new \OfxParser\Parser();
$ofx = $ofxParser->loadFromFile('/path/to/your/bankstatement.ofx');

$bankAccount = reset($ofx->bankAccounts);

// Get the statement start and end dates
$startDate = $bankAccount->statement->startDate;
$endDate = $bankAccount->statement->endDate;

// Get the statement transactions for the account
$transactions = $bankAccount->statement->transactions;
```

Most common nodes are support. If you come across an inaccessible node in your OFX file, please submit a pull request!

## Investments Support

Investments support was remove in this version. Please refer to original package : [okonst/ofxparser](https://github.com/okonst/ofxparser)

## Fork & Credits

This is a fork of [oriatec/ofxparser](https://github.com/oriatec/ofxparser), itself forked of [okonst/ofxparser](https://github.com/okonst/ofxparser) made to be framework independent. The source repo was designed for Symfony 2 framework, so credit should be given where credit due!
Heavily refactored by [Oliver Lowe](https://github.com/loweoj) and loosely based on the ruby [ofx-parser by Andrew A. Smith](https://github.com/aasmith/ofx-parser).
