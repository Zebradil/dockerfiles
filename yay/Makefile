ifndef PACMAN_MIRROR
	PACMAN_MIRROR = $(shell sh -c 'grep "^Server" /etc/pacman.d/mirrorlist | head -n1 | cut -d" " -f3' 2>/dev/null)
endif

ifeq ($(PACMAN_MIRROR),)
    PACMAN_MIRROR = http://arch.jensgutermuth.de/$$repo/os/$$arch
endif

build:
	docker build -t yay --build-arg PACMAN_MIRROR='$(PACMAN_MIRROR)' .
