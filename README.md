# virt-manager


Simple docker image for running [virt-manager](https://virt-manager.org/) in a container.

## Usage

virt-manager needs access to X11 to run.  There are several ways to accomplish
this, and the solution will depend on your platform.

### Linux

TODO: fully document this (maybe a blog post)

### OSX

TODO: fully document this (maybe a blog post)

To run virt-manager on Linux, for instance, try:

```shell
$ docker run \
	--rm -it \
	-v /tmp/.X11-unix:/tmp/.X11-unix \
	-v /tmp/.virt-manager.xauth:/tmp/.virt-manager.xauth \
	-e XAUTHORITY=/tmp/.virt-manager.xauth \
	-e DISPLAY=unix$DISPLAY:0 \
	--name virt-manager \
	jdubz/virt-manager
```

An example bash function that wraps the entire command, allowing the user to simply execute `ansible` and run the entire build process in a container automatically, can be found [here](https://github.com/t3hpr1m3/dotfiles/blob/51d1e76c63d741a29edefdf1d1f9ef14351fbb3e/home/.docker_wrappers#L1).

## License

Released under the [MIT License](http://www.opensource.org/licenses/MIT).
