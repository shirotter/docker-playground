# Stage A
FROM busybox:latest AS stage-A

ARG arg_a="arg A"
ENV env_a="env A"

# Stage B
FROM busybox:latest AS stage-B

ARG arg_a
ARG arg_b="arg B"

ENV env_b="env B"

RUN set -x \
    && echo "${arg_a:-undefined arg [arg_a]}" \
    && echo "${arg_b:-undefined arg [arg_b]}" \
    && echo "${env_a:-undefined env [env_a]}" \
    && echo "${env_b:-undefined env [env_b]}"
