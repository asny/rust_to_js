# rust_to_js
Hello world example of Rust, OpenGL and SDL2 which supports compilation to javascript and WebGL 2.0.

* Easy compilation for both desktop and web
* Guarantee that only features supported by WebGL 2.0 is used
* Possible to preload resources (see https://kripken.github.io/emscripten-site/docs/porting/files/packaging_files.html)

# Installation
### Rust
```$ curl https://sh.rustup.rs -sSf | sh```
Logout and in again

### SDL2
```$ brew install sdl2```

### rust_to_js
```$ git clone https://github.com/asny/rust_to_js.git rust_to_js```

### Emscripten
```$ cd ~/```

```$ git clone https://github.com/juj/emsdk .emsdk```

```$ cd .emsdk/```

```$ ./emsdk install latest```

```$ ./emsdk activate latest```

```$ source ./emsdk_env.sh```

Change embuilder.py to use python (may not be necessary)

```$ embuilder.py build sdl2```

```$ rustup target add asmjs-unknown-emscripten```

# Compilation
cd to rust_to_js project folder

### Desktop
```$ cargo run```

### Web
```$ ./buildToWeb```

```$ python -m SimpleHTTPServer```

Go to http://localhost:8000/

### Clean
```$ ./clean```

# Sources:
https://www.rust-lang.org/en-US/install.html
https://blog.fazibear.me/definitive-guide-to-rust-sdl-2-and-emscripten-93d707b22bbb
http://nercury.github.io/rust/opengl/tutorial/2018/02/08/opengl-in-rust-from-scratch-00-setup.html
