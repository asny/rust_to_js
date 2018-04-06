# rust_to_js
Hello world example of Rust, OpenGL and SDL2 which supports ci to javascript and WebGL 2.0

# Installation
### Rust
$ curl https://sh.rustup.rs -sSf | sh
- Logout and in again
(https://www.rust-lang.org/en-US/install.html)

### SDL2
$ brew install sdl2

### Test installation
$ git clone https://github.com/asny/rust_to_js.git rust_to_js
$ cd rust_to_js
$ cargo run
(https://doc.rust-lang.org/cargo/getting-started/first-steps.html)

### Emscripten
$ cd ~/
$ git clone https://github.com/juj/emsdk .emsdk
$ cd .emsdk/
$ ./emsdk install latest
$ ./emsdk activate latest
$ source ./emsdk_env.sh

### Emscripten + SDL2
- Change embuilder.py to use python (may not be necessary)
$ embuilder.py build sdl2

### Test installation
- cd to rust_to_js project folder
$ rustup target add asmjs-unknown-emscripten
$ cargo run
$ ./buildToWeb
$ python -m SimpleHTTPServer
Go to http://localhost:8000/

# Sources:
https://blog.fazibear.me/definitive-guide-to-rust-sdl-2-and-emscripten-93d707b22bbb
http://nercury.github.io/rust/opengl/tutorial/2018/02/08/opengl-in-rust-from-scratch-00-setup.html
