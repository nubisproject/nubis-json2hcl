# nubis-json2hcl

This is a small docker container (8.31MB) containing json2hcl.

Run it like:

```bash
echo 'arena = "core"' | docker run -i nubis-json2hcl -reverse
```

Or in a script like:

```bash
ARENA=$(docker run -i nubis-json2hcl -reverse \
    < ${TERRAFORM_PATH}/terraform.tfvars \
    | docker run -i nubis-jq jq --raw-output .arena)
echo "ARENA: ${ARENA}"
```
