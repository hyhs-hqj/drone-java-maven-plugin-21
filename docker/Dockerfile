FROM docker.io/library/maven:3.9-eclipse-temurin-21-alpine
LABEL org.opencontainers.image.source https://github.com/hyhs-hqj/drone-java-maven-plugin-21
LABEL org.opencontainers.image.authors="Gavin"

LABEL description="A Drone plugin to build Java applications using Apache Maven"
LABEL MAVEN_VERSION=3.9
LABEL JAVA_VERSION=21

RUN apt-get update \
  && apt-get install -y ca-certificates \
  && rm -rf /var/lib/apt/lists/*

# TODO: enable to run as non-root
# RUN adduser --system --uid 1001 dev \
#     && mkdir -p /home/dev/.m2 \
#     && chown 1001:0 /home/dev/.m2

ADD run.sh /bin/
RUN chmod +x /bin/run.sh

# TODO: enable to run as non-root
# USER dev

# TODO: enable to run as non-root
# ENV USER_HOME_DIR=/home/dev
# ENV MAVEN_CONFIG=/home/dev/.m2

CMD ["/bin/run.sh"]
