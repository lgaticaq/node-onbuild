# node-onbuild

[![dockeri.co](http://dockeri.co/image/lgatica/node-onbuild)](https://hub.docker.com/r/lgatica/node-onbuild/)

[![Build Status](https://travis-ci.org/lgaticaq/node-onbuild.svg?branch=master)](https://travis-ci.org/lgaticaq/node-onbuild)

> Docker onbuild image for node apps with alpine linux

Supported tags and respective Dockerfile links

* 10.4.1, 10.4, 10, latest ([10.4/Dockerfile](https://github.com/lgaticaq/node-onbuild/blob/master/10.4.1/Dockerfile))
* 9.11.2, 9.11, 9 ([9.11/Dockerfile](https://github.com/lgaticaq/node-onbuild/blob/master/9.11.2/Dockerfile))
* 8.11.3, 8.11, 8 ([8.11/Dockerfile](https://github.com/lgaticaq/node-onbuild/blob/master/8.11.3/Dockerfile))
* 6.14.3, 6.14, 6 ([6.14/Dockerfile](https://github.com/lgaticaq/node-onbuild/blob/master/6.14.3/Dockerfile))

## Create a Dockerfile in your Node.js app project

```dockerfile
FROM lgatica/node-onbuild:10.4.1
EXPOSE 3000
```

You can then build and run the Docker image:

```bash
docker build -t my-nodejs-app .
docker run -it --rm --name my-running-app my-nodejs-app
```

### Notes

The image assumes that your application has a file named package.json listing its dependencies and defining its start script.
