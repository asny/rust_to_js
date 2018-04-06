# rust_to_js
Hello world example of compiling Rust and OpenGL 4.3 to javascript and WebGL 2.0

# Installation and use

## Rust: Install
$ curl https://sh.rustup.rs -sSf | sh
- Logout and in again
(https://www.rust-lang.org/en-US/install.html)

## Rust: Use
$ cargo new hello_world --bin
$ cd hello_world
$ cargo run
(https://doc.rust-lang.org/cargo/getting-started/first-steps.html)

## SDL2: Install
$ brew install sdl2

## SDL2: Use
- Add sdl2 = “0.29.0” to Cargo.toml dependencies
- Modify src/main.rs to use sdl2 (e.g. https://gist.githubusercontent.com/fazibear/c81677c67457b96d1809f9d7492f9a60/raw/7c9e71d6133012f5ec7d9c72ea6a12b93bb92692/main0.rs)
$ cargo run

## Emscripten: Install
$ cd ~/
$ git clone https://github.com/juj/emsdk .emsdk
$ cd .emsdk/
$ ./emsdk install latest
$ ./emsdk activate latest
$ source ./emsdk_env.sh

## Emscripten: Compile SDL2
- Change embuilder.py to use python
$ embuilder.py build sdl2
$ export EMMAKEN_CFLAGS="-s USE_SDL=2"

## Emscripten: Use
- cd to hello_world project folder
$ rustup target add asmjs-unknown-emscripten
- Modify src/main.rs to use emscripten (e.g. https://gist.githubusercontent.com/fazibear/9ce5287dcb75117d8691393c7d3f626d/raw/2fac8407fe7d966f3d1d640d8799b2ae1a4f9ec7/main1.rs)
- Add src/emscripten.rs (e.g. https://gist.githubusercontent.com/fazibear/4624a1c8cb2c7edd723e7a754681de16/raw/405ee9342cbb0dc89eca948af142dd5566c01879/emscripten.rs)
$ cargo run
$ cargo build --target asmjs-unknown-emscripten

## Emscripten: Rebuild
$ source ~/.emsdk/emsdk_env.sh
$ export EMMAKEN_CFLAGS="-s USE_SDL=2"
$ cargo build --target asmjs-unknown-emscripten

## Web
Add index.html
$ python -m SimpleHTTPServer
Go to http://localhost:8000/

## Source:
(https://blog.fazibear.me/definitive-guide-to-rust-sdl-2-and-emscripten-93d707b22bbb)
