# TOT professional, in the browser

TOT PROFESSIONAL is a 1984 Commodore 64 program for building reduced
Totocalcio systems, published by TOTOCOMMODORE. This is a reimplementation in
Rust, written from the reverse-engineering notes of the original rather than
from its code, compiled to WebAssembly and rendered into a 40x25 text screen.

**Play it: https://aovestdipaperino.github.io/totpro-demo/**

The screens are the original ones, in English by default and in the verbatim
Italian of the 1984 binary at the flick of a switch. The two logo screens the
program opened with are left out here, since the page carries its own. What runs behind them is
the real engine: the odometer that enumerates a development without ever
building a list of it, and the conditioning filters a *sistemista* used to
throw columns away.

Where the disk shipped ten covering designs for three to seven doubles, this
build reduces with the provably smallest system that still guarantees a twelve
out of thirteen: the perfect ternary Hamming code of length 13, 59,049 columns
of the 1,594,323 possible.

## Keys

| Key | Effect |
| --- | --- |
| `1` `X` `2` | toggle a sign on the highlighted match |
| `up` `down` | move within a grid, list or menu |
| `Y` or `S` / `N` | answer a yes/no prompt |
| `TAB` `+` `-` | move between `MIN.`/`MAX.` and adjust them |
| `N` / `P` | next and previous page of the column listing |
| `RETURN` | confirm the current field |
| `ESC` | step back one screen |

## Building this page

`index.html` is generated, not written: it is the Rust crate's WebAssembly
build with the `.wasm` inlined as base64, so the page runs with no other
requests. It is rebuilt from the crate with `./build-web.sh` followed by
`python3 web/build-single-file.py`.
