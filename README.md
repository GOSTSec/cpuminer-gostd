Run with your gostcoin wallet app
```bash
./minerd -a gostd -t <number of cores> -o http://127.0.0.1:9376 -u <your RPC user> -p <you RPC password>
```

Building on most linux distributions. Install libcurl and libjansson development packages first!
```bash
./autogen.sh
LIBCURL="-lcurl" ./configure CFLAGS="-O3"
make
```

Building on Windows is possible with MSYS2.
```bash
./autogen.sh
./configure CFLAGS="-O3 -DCURL_STATICLIB" --with-libcurl=compat/curl-win-x86_64
make
```
