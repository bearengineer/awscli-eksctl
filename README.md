# awscli-eksctl

# What is awscli?

> Awscli is the Amazon web services command line interface.

[Overview of awscli](https://docs.aws.amazon.com/cli/index.html)

# What is eksctl?

> `eksctl` is a simple CLI tool for creating clusters on EKS - Amazon’s new managed Kubernetes service for EC2.

[Overview of eksctl](https://eksctl.io/introduction/getting-started/)

# TL;DR;

```bash
$ docker run -ti --rm bearengineer/awscli-eksctl
```

```bash
$ docker run -ti -e 'AWS_ACCESS_KEY_ID=********************' -e 'AWS_SECRET_ACCESS_KEY=****************************************' --rm bearengineer/awscli-eksctl eksctl get clusters
```

```bash
$ docker run -ti -v '/Users/bearengineer/.aws:/root/.aws' --rm bearengineer/awscli-eksctl eksctl get clusters
```


# Supported tags and respective `Dockerfile` links

* [`awscli-1.16-eksctl-0.5`, `latest` (Dockerfile)](https://github.com/bearengineer/awscli-eksctl/blob/Dockerfile)

Subscribe to project updates by watching the [bearengineer/awscli-eksctl GitHub repo](https://github.com/bearengineer/awscli-eksctl).

# Get this image

The recommended way to get the Bear Engineer awscli-eksctl Docker Image is to pull the prebuilt image from the [Docker Hub Registry](https://hub.docker.com/r/bearengineer/awscli-eksctl).

```bash
$ docker pull bearengineer/awscli-eksctl:latest
```

To use a specific version, you can pull a versioned tag. You can view the [list of available versions](https://hub.docker.com/r/bearengineer/awscli-eksctl/tags/) in the Docker Hub Registry.

```bash
$ docker pull bearengineer/awscli-eksctl:[TAG]
```

If you wish, you can also build the image yourself.

```bash
$ docker build -t bearengineer/awscli-eksctl:latest 'https://github.com/bearengineer/awscli-eksctl.git#master'
```

# Configuration

## Running commands

To run commands inside this container you can use `docker run`, for example to execute `eksctl --version` you can follow the example below:

```bash
$ docker run --rm --name eksctl bearengineer/awscli-eksctl:latest -- eksctl version
```

Consult the [eksctl Reference Documentation](https://eksctl.io/usage/creating-and-managing-clusters/) or the [AWS CLI Reference Documentation](https://docs.aws.amazon.com/cli/index.html) to find the completed list of commands available.

## AWS Credentials

AWS credentials can either be passed by environment variables, or by mounting a volume with aws credentials file under `/root/.aws`.

### Environment variables

```bash
$ docker run -ti -e 'AWS_ACCESS_KEY_ID=********************' -e 'AWS_SECRET_ACCESS_KEY=****************************************' --rm bearengineer/awscli-eksctl aws s3 ls
```

### AWS directory

```bash
docker run -ti -v '/Users/bearengineer/.aws:/root/.aws' --rm bearengineer/awscli-eksctl aws s3
```

# Contributing

We'd love for you to contribute to this container. You can request new features by creating an [issue](https://github.com/bearengineer/awscli-eksctl/issues), or submit a [pull request](https://github.com/bearengineer/awscli-eksctl/pulls) with your contribution.

# Issues

If you encountered a problem running this container, you can file an [issue](https://github.com/bearengineer/awscli-eksctl/issues). For us to provide better support, be sure to include the following information in your issue:

- Host OS and version
- Docker version (`docker version`)
- Output of `docker info`
- Version of this container
- The command you used to run the container, and any relevant output you saw (masking any sensitive information)

# License

Copyright (c) 2019 Bear Engineer. All rights reserved.

This work is licensed under the terms of the MIT license.  
For a copy, see <https://opensource.org/licenses/MIT>.

