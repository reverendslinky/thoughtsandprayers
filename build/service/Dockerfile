FROM alpine:3.7


# --- Install packages we know we'll need
RUN apk add --no-cache curl openjdk8

# --- Some likely temporary helper packages while we're developing
RUN apk add --no-cache shadow bash 

# --- Setup worker user ---
RUN addgroup -S worker && \
    adduser -S -G worker -h /home/worker -D worker


# --- Install Gradle ---
RUN cd /usr/lib && \
    curl -fsSL https://services.gradle.org/distributions/gradle-4.7-bin.zip -o gradle-bin.zip && \
    unzip gradle-bin.zip && \
    ln -s "/usr/lib/gradle-4.7/bin/gradle" /usr/bin/gradle && \
    rm gradle-bin.zip
    
ENV GRADLE_HOME /usr/lib/gradle
ENV PATH $PATH:$GRADLE_HOME/bin

USER worker
WORKDIR /home/worker
CMD ["gradle"]
