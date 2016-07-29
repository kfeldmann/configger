Configger
=========

Merge, substitute variables, and compress multiple cloud-config files
into one.

Cloud-config is a file format used by cloud-init, which is used to
bootstrap cloud server instances.

```
$ ./cf
Usage: cf [-s] cloud-configs.yml
    -s
       The argument is a YAML string, rather than a filename.
```
## Example input YAML data
```YAML
# If output-file is null, stdout will be used.
output-file: user-data.yml

variable-mapping:
  key: value
  key: value
  ...

cloud-configs:
- file.yml
- file.yml
  ...
```
