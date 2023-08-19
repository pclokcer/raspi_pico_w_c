build and run
```sh
cmake -G "MinGW Makefiles" ..
make
```

after
```sh
nodemon --watch "./" --ext "c" --exec "cd ./build && cmake -G \"MinGW Makefiles\" .. && make"
```

Development Tools
- [cmake install](https://cmake.org/download/)
- mingw64
- nodemon