# random-log

Docker image for a random log generator, based on Alpine Linux.

![release](https://github.com/moroleandro/random-log)

## What is this?

This image will execute a container which will generate four random log messages:

* `2018-03-02T22:33:27-06:00 ERROR something happened in this execution.`
* `2018-03-02T22:33:27-06:00 INFO takes the value and converts it to string.`
* `2018-03-02T22:33:27-06:00 WARN variable not in use.`
* `2018-03-02T22:33:27-06:00 DEBUG first loop completed.`

## Why this Image?

I've had the necessity to create a random logger to test log configurations with containers, this helped me out to do it easily.

## What is inside of this repo?

In this git repository you will find the docker image definitions for the random Logger for Alpine Linux

* `Dockerfile` -> Contains image definition.
* `entrypoint.sh` -> Shell code to generate log messages.

## How do I use this image?

To use this image you must do as follows:

```bash
# you can use tags latest
docker pull moroleandro/random-log:latest

# use different intervals to print logs every random(100, 400) milliseconds
docker run moroleandro/random-log:latest 100 400

# use the third parameter so limit the number of loglines (after generating the lines the container will stop).
# if not set it runs infinite
docker run moroleandro/random-log:latest 100 400 100

# to run the image just execute
docker run -d moroleandro/random-log:latest
```

You will have now a docker container running and generating log messages, locate it running:

```bash
docker ps
```

You can see the logs using this command

```bash
docker logs <- container-id ->
```

## How do I build this images?

First things first, you can find these docker images in `moroleandro/random-log`
but you can also build a specific version on your own, you only need:

* docker
* git

Clone this repo

`git clone https://github.com/moroleandro/random-log.git`

Go to the folder in your terminal and type this:

```bash
# cd into folder
cd random-log
# Then build the new image
docker build -f Dockerfile .
```

If you want to tag your image use the following command

```bash
docker build -f Dockerfile -t yourbase/yourname:version .
```

---

You can get the source from the image in the [Repository](https://github.com/moroleandro/random-log)

## Author

@moroleandro

