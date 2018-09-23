# Behavior of ARG and ENV in multi-stage-build

## Summary

![#c5f015](https://placehold.it/15/f03c15/000000?text=+) ARG and ENV are not shared between stages.

## Test process

### Use build-arg option

```bash
$ docker build --rm --build-arg arg_a="build arg A" -t playground .

+ echo 'build arg A'
+ echo 'arg B'
+ echo 'undefined env [env_a]'
+ echo 'env B'
```

### Not use build-arg option

```bash
$ docker build --rm -t playground .

+ echo 'undefined arg [arg_a]'
+ echo 'arg B'
+ echo 'undefined env [env_a]'
+ echo 'env B'
```
