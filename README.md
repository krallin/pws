pws [![[travis]](https://travis-ci.org/janlelis/pws.png)](https://travis-ci.org/janlelis/pws)
===
pws is a command-line password safe/manager written in Ruby using [aes-256-cbc](http://en.wikipedia.org/wiki/Advanced_Encryption_Standard) and [pbkdf2](http://en.wikipedia.org/wiki/PBKDF2).


Usage
---
[![Screenshot](https://ruby.janlelis.de/pws-example.png)](https://ruby.janlelis.de/60-pws-the-ruby-powered-command-line-password-manager)


Setup
---
You can install *pws* with: `$ gem install pws`

Run `$ pws --help` for usage information.

On Linux, please make sure you've got `xclip` or `xsel` installed (for the clipboard).

Hints
---

### OpenSSL 1.0
You should use a Ruby that was built with bindings to an openssl version >= 1.0 or pws will fall back to a Ruby-only version of the PBKDF2 function, which is much slower. If using openssl 1.0 is not possible for you, you can work around that issue by using the `--iterations` option with a value below 75\_000 (see help). If you have problems using openssl 1.0 with your Ruby, please look for a solution in [this issue](https://github.com/janlelis/pws/issues/7).


### Updating from pws 0.9
The 0.9 password files are not compatible with the 1.0 version of pws, however, you can convert your safe with:
`$ pws resave --in 0.9 --out 1.0`


### How to use a .pws file in the current working directory
Besides using the `--filename path/to/safe` option, you can shortly call `pws --cwd` for using a `.pws` file in the current directory.


### Reading the source
Trust the code by reading the source! It's originally based on [this tutorial](https://ruby.janlelis.de/41-tutorial-build-your-own-password-safe-with-ruby). You might want to start reading in the [0.9.2 tag](https://github.com/janlelis/pws/tree/0.9.2), because it's got less features and therefore is less code.


Projects built on top of PWS
---
* [pws-otp](https://github.com/janlelis/pws-otp) Experimental OTP support for 2FA
* [pwsqr](https://github.com/smileart/pwsqr) Simple QR interface to pws gem. Helps to use your passwords on a smartphone.
* [aws-pws](https://github.com/fancyremarker/aws-pws) A password-protected CredentialProvider for AWS
* [omnivault](https://github.com/aptible/omnivault) Multi-platform keychain functionality


Blog articles
---
* [Packaging ruby programs in NixOS](http://blog.arkency.com/2016/04/packaging-ruby-programs-in-nixos/) using PWS as example


Contributors
---
* [namelessjon](https://github.com/namelessjon/)
* [brianewing](https://github.com/brianewing/)
* [dquimper](https://github.com/dquimper/)
* [grapz](https://github.com/grapz/)
* [thecatwasnot](https://github.com/thecatwasnot/) (cucumber specs loosely based on [these](https://github.com/thecatwasnot/passwordsafe/blob/master/features/))


J-\_-L
---
© 2010-2017 Jan Lelis, MIT license
