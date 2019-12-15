# YAY

Dockerized version of [yay].  
Useful for debugging [PKGBUILD] files in isolated environment.

## Usage

```bash
# First, build the image
make build

# Or specify your favorite pacman mirror:
make build PACMAN_MIRROR=https://mirror.arizona.edu/archlinux/$repo/os/$arch

# Run
docker run -it yay

# Have fun
yay rustotpony
```

[yay]: https://github.com/Jguer/yay
[PKGBUILD]: https://wiki.archlinux.org/index.php/PKGBUILD
