# Behavior of ARG and ENV in multi-stage-build

## Use build-arg option

```bash
$ docker build --rm --build-arg arg_a="build arg A" -t playground .

+ echo 'build arg A'
+ echo 'arg B'
+ echo 'undefined env [env_a]'
+ echo 'env B'
```

## Not use build-arg option

```bash
$ docker build --rm -t playground .

+ echo 'undefined arg [arg_a]'
+ echo 'arg B'
+ echo 'undefined env [env_a]'
+ echo 'env B'
```
