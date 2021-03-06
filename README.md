# LastPass Auditor

This is a simple CLI that will read a CSV export of your LastPass passwords and check them against the known pwned passwords on [haveibeenpwned](https://haveibeenpwned.com/).

## How does it work?

Your plaintext passwords are safe (as long as you protect your CSV export) and are not transmitted over the internet. The beginning of the sha1 hash of your password is sent over the internet to find potential matches, but the full sha1 is never sent over the internet; all full hash comparison is done locally. You can read more about the haveibeenpwned api [here](https://haveibeenpwned.com/API/v2#SearchingPwnedPasswordsByRange).

## Install

If you have golang installed, you can download the code:

```
go get -u github.com/scnewma/lpass-auditor
```

Otherwise you can download one of the pre-compiled releases from the [releases page](https://github.com/scnewma/lpass-auditor/releases).

## Usage

This CLI requires a CSV export of your LastPass data. You can do that via the browser extension under `More Options > Advanced > Export`. After exporting, you can run the lpass-auditor CLI.

```
lpass-auditor /path/to/csv
```