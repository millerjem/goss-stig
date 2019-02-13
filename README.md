At attempt to recreate [DISA STIG](https://iase.disa.mil/stigs/os/unix-linux/Pages/index.aspx) checks for RedHat Enterprise Linux 7
with [goss](https://github.com/aelsabbahy/goss/). It is intended to serve as a foundation for your own checks.

## Usage

To use it, get goss binary from https://github.com/aelsabbahy/goss/ and run: 

``` 
goss -g goss-stig.yaml validate
``` 

## Benefits
I choose `goss` over other frameworks for its performance (200+ tests not requiring `rpm` invocation complete in under 2 seconds on
a small DO VM) and no dependencies (it's a single static binary). `goss` uses YAML as a configuration file format which is easier to
write and read than XML (hence, no XCCDF and OpenSCAP).

`goss` could be started as a healthcheck-like service (see `serve` subcommand) and used with your monitoring.

## Links
- [Automated Security Auditing of EL Based Linux Systems](https://github.com/aaron868/security-audit) implemented with
  [serverspec](https://serverspec.org).
- Slides of my [presentation on using goss](https://bit.ly/2IbMA3e) to check server conguration in test-driven-security style
- RHEL 7 STIG on [STIG viewer](https://www.stigviewer.com/stig/red_hat_enterprise_linux_7/)
