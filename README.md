# rust_to_js
Hello world example of Rust, OpenGL and SDL2 which supports compilation to JavaScript/WebAssembly and WebGL 2.0.

* Easy compilation for both desktop and web (both WebAssembly and JavaScript)
* Guarantee that only features supported by WebGL 2.0 is used
* Possible to preload resources (see https://kripken.github.io/emscripten-site/docs/porting/files/packaging_files.html)

# Installation
### Rust
```$ curl https://sh.rustup.rs -sSf | sh```

Logout and in again

(See also https://www.rust-lang.org/en-US/install.html)

### SDL2
```$ brew install sdl2```

### Emscripten
```$ cd ~/```

```$ git clone https://github.com/juj/emsdk .emsdk```

```$ cd .emsdk/```

```$ ./emsdk install latest```

```$ ./emsdk activate latest```

```$ source ./emsdk_env.sh```

(See also https://kripken.github.io/emscripten-site/docs/getting_started/downloads.html)

### Emscripten + SDL2
```$ embuilder.py build sdl2``` (It might be necessary to change embuilder.py to use python)

### Emscripten + Rust
```$ embuilder.py build binaryen``` (It might be necessary to change embuilder.py to use python)

```$ rustup target add asmjs-unknown-emscripten```

```$ rustup target add wasm32-unknown-emscripten```

### rust_to_js
```$ git clone https://github.com/asny/rust_to_js.git rust_to_js```

# Compilation
cd to rust_to_js project folder

### Desktop
```$ cargo run```

### Web
```$ ./toJS``` or ```$ ./toWasm```

```$ python -m SimpleHTTPServer```

Go to http://localhost:8000/

### Clean
```$ ./clean```

# Sources:
- https://blog.fazibear.me/definitive-guide-to-rust-sdl-2-and-emscripten-93d707b22bbb
- http://nercury.github.io/rust/opengl/tutorial/2018/02/08/opengl-in-rust-from-scratch-00-setup.html
