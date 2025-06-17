# moodle-docker-php

docker build -t php-moodle:8.4-fpm



https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-container-registry


export CR_PAT=ghp_a


echo $CR_PAT | docker login ghcr.io -u vkovalok --password-stdin

docker push ghcr.io/tsmu-hub/IMAGE_NAME:latest


docker tag e79d05541db8 ghcr.io/tsmu-hub/php-moodle:latest
# LABEL org.opencontainers.image.source https://github.com/tsmu-hub/moodle-docker-php