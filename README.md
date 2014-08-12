# docker-centos-general-rpmbuild-environment

This Dockerfile provides immutable RPM build machine/infrastructure with Docker for CentOS6.x environment.

## Usage

##### Step1: Build an image

`docker build` to create base template image file localy.

```sh
$ docker build --rm -t y_ken/centos_rpmbuild_env github.com/y-ken/docker-centos-general-rpmbuild-environment.git
```

After finished build, you can see new image like below.

```sh
$ docker images
REPOSITORY                      TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
y_ken/centos_rpmbuild_env       latest              3c4b9336e10b        34 seconds ago      1.045 GB
centos                          centos6             539c0211cd76        12 days ago         212.5 MB
```

###### Step2: Boots up the machine

`docker run` to execute the virtual machie from base template everytime.<br>

```sh
$ docker run -i -t y_ken/centos_rpmbuild_env /bin/bash --login
```

If you don't want containers to persist after you shutdown add the --rm option like so.<br>

```sh
$ docker run -i -t --rm y_ken/centos_rpmbuild_env /bin/bash --login
```

## Specifications

##### rpmbuild path

* root : /root/rpmbuild
* build : /home/build/rpmbuild

**Note**<br>
To switch general build user, type `su - build` command.

## TODO

Pull requests are very welcome!!

## Copyright

Copyright © 2014- Kentaro Yoshida ([@yoshi_ken](https://twitter.com/yoshi_ken))

## License

* MIT License http://www.opensource.org/licenses/mit-license.php
