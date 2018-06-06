This dockerfile creates the builder for any java-based service.

It's prepackaged with openjdk and gradle.


OKAY! Quick recap on how this whole thing works:
* The container has java and gradle installed.
* You mount your local directory in to the container, all changes are mutually reflected.
That's really it.

Here's a few examples:
docker run --rm -v <local directory>:/home/worker/ builder:1 gradle build
docker run --rm -v <local directory>:/home/worker/ builder:1 gradle check
docker run --rm -v <local directory>:/home/worker/ builder:1 gradle init

