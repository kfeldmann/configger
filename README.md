Configger
=========

Merge, substitute variables, and compress multiple cloud-config files
into one.

Cloud-config is a file format used by [cloud-init](https://launchpad.net/cloud-init),
which is used to bootstrap cloud server instances.

```
$ ./cf
Usage: cf [-s] cf-configuration.yml
    -s
       The argument is a YAML string, rather than a filename.
```
## Example cf-configuration YAML data
```YAML
# If output-file is null, stdout will be used.
output-file: user-data.yml

# Use 'base64' here to encode the entire output as one line
# of base64 (useful in an AWS launch-template)
output-encoding: null

variable-mapping:
  key: value
  key: value
  ...

cloud-configs:
- file.yml
- file.yml
  ...
```
## Environment variables
The following environment variables can be used for troubleshooting:
* `DEBUG` - Turn on debugging output
* `NOCOMPRESS` - Do not compress or encode the merged cloud-config
