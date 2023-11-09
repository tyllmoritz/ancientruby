.PHONY: all clean

CC := gcc
CFLAGS := -O3 -std=c99 -Wall -Wextra

tools := \
	lzcomp \
	png_dimensions \
	scan_includes \
	palette \
	pokemon_animation \
	pokemon_animation_graphics \
	gfx \
	md5
all: $(tools)
	@:

lzcomp: CFLAGS += -flto -Wno-strict-overflow -Wno-sign-compare
lzcomp: $(wildcard lz/*.c) $(wildcard lz/*.h)
	$(CC) $(CFLAGS) -o $@ lz/*.c

clean:
	rm -f $(tools)

gfx md5: common.h
%: %.c
	$(CC) $(CFLAGS) -o $@ $<
