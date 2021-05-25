# check_gpg_expiry

Icinga check command to show expiring pgp keys

## Requirements

* python3
* GNU Privacy Guard suite (gpg)
* file command

## Usage

### Arguments
```
optional arguments:
  -h, --help            show this help message and exit
  -w [WARNING], --warning [WARNING]
                        Warning threshold, default 604800 seconds (one week)
  -c [CRITICAL], --critical [CRITICAL]
                        Critical threshold, default 0 seconds
  -d DIRS [DIRS ...], --dirs DIRS [DIRS ...]
                        Directories to check for pgp keys in
  -s, --sort            Sort by expiry date, sorts by path otherwise
  -v, --verbose         Verbose output
  -e, --expiring        Only show expiring keys,requires -v/--verbose to actually do
                        something
```

### Examples


Normal output:
```
check_gpg_expiry -d /etc/pki/rpm-gpg/
OK - All keys ok
```

Verbose output:
```
check_gpg_expiry -d /etc/pki/rpm-gpg/ -vs
OK - All keys ok

/etc/pki/rpm-gpg/RPM-GPG-KEY-fedora-iot-2019:
    Algorithm: 1
    Length: 4096
    Issue Date: 1542132312 - 13-11-2018
    Expiry Date: 1861833600 - 31-12-2028

/etc/pki/rpm-gpg/RPM-GPG-KEY-fedora-31-primary:
    Algorithm: 1
    Length: 4096
    Issue Date: 1550507267 - 18-02-2019
    Expiry Date: 1866067200 - 18-02-2029

/etc/pki/rpm-gpg/RPM-GPG-KEY-fedora-modularity:
    Algorithm: 1
    Length: 4096
    Issue Date: 1494955923 - 16-05-2017
    Expiry Date: 2177366400 - 31-12-2038

/etc/pki/rpm-gpg/RPM-GPG-KEY-fedora-10-primary:
    Algorithm: 17
    Length: 1024
    Issue Date: 1219877875 - 28-08-2008
    Expiry Date: None

/etc/pki/rpm-gpg/RPM-GPG-KEY-fedora-11-primary:
    Algorithm: 1
    Length: 4096
    Issue Date: 1232406641 - 20-01-2009
    Expiry Date: None

/etc/pki/rpm-gpg/RPM-GPG-KEY-fedora-12-primary:
    Algorithm: 1
    Length: 4096
    Issue Date: 1248827311 - 29-07-2009
    Expiry Date: None

/etc/pki/rpm-gpg/RPM-GPG-KEY-fedora-13-primary:
    Algorithm: 1
    Length: 4096
    Issue Date: 1263942876 - 20-01-2010
    Expiry Date: None
```
