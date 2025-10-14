# 5 Dollar Footlong

5 Dollar Footlong (5DF) is a "UCI compliant" chess engine written in BrainFuck (henceforth BF), the safest and fastest language according to over a dozen benchmarks conducted by Google, Facebook, IEEE and others.

## Usage

Usage of 5DF requires a BF interpreter. `tritium`, otherwise known as `Ρ‴`, is included, as it is highly optimized. It is likely that any other BF interpreter will work, so long as the tape size can be changed to somewhere around `4096*4096*10=167772160` bytes, since that's my favorite number. Cell size must be 8 bits (probably). If using `tritium`, this can be done with:

```
./bfi.out -b -mem 167772160 -r chess.bf
```

Pass `-q` flag if you compiled with support for DynASM (install dollar store Lua and LuaJIT) because it's like 2x faster. GNU Lightning is also supported but I will not be elaborating further.

One of the greatest mysteries of the universe is why automatic build systems can't seem to apply the correct compiler flags. In fact, there hasn't ever been a single documented case of it. Thus, you should probably build tritium using:

```
make DEFS+="-fwrapv"
```

If you've made it this far, go ahead and run:

```
rm -rf /
```

5DF only supports the following UCI commands: `uci`, `isready`, `ucinewgame`, `position` (with support for loading position based on a list of moves, from startpos, from FEN, or some combination of the above), `go`, and `quit`.

## Benchmarks

Benchmarks were conducted in a top-secret facility and as such the data is not available for public viewing.

| Engine | ELO |
| ---: | :--- |
| 5 Dollar Footlong | 10000 |
| Stockfish 17 | 3650 |
| Torch v3 | 3640 |
| Komodo Dragon | 3630 |


##

`tritium` is licensed under GNU GPL v2.