$ git clone https://github.com/icio/go-get-panic
Cloning into 'go-get-panic'...
remote: Enumerating objects: 7, done.
remote: Counting objects: 100% (7/7), done.
remote: Compressing objects: 100% (5/5), done.
remote: Total 7 (delta 1), reused 7 (delta 1), pack-reused 0
Receiving objects: 100% (7/7), done.
Resolving deltas: 100% (1/1), done.

$ cd go-get-panic

$ git checkout 2cbc2db2a48105fa2b71ec69d11b6496ba52c263

$ git rev-parse HEAD
2cbc2db2a48105fa2b71ec69d11b6496ba52c263

$ gotip version
go version devel go1.20-e09bbae Sat Oct 29 04:48:07 2022 +0000 linux/amd64

$ gotip get -u golang.org/x/tools
panic: internal error: can't find reason for requirement on golang.org/x/sync@v0.0.0-20220601150217-0de741cfad7f

goroutine 1 [running]:
cmd/go/internal/modget.(*resolver).updateBuildList.func1({{0xc0000281e0, 0x11}, {0xc000032690, 0x22}})
        /home/icio/sdk/gotip/src/cmd/go/internal/modget/get.go:1760 +0xd4
cmd/go/internal/modget.(*resolver).updateBuildList(0xc00023c000, {0xb2d5d0, 0xc00002c0f8}, {0x0, 0x0, 0x0})
        /home/icio/sdk/gotip/src/cmd/go/internal/modget/get.go:1765 +0x54c
cmd/go/internal/modget.(*resolver).resolveQueries(0xc00023c000, {0xb2d5d0, 0xc00002c0f8}, {0xc000014058, 0x1, 0xc0000a3d78?})
        /home/icio/sdk/gotip/src/cmd/go/internal/modget/get.go:1243 +0x1a5
cmd/go/internal/modget.runGet({0xb2d5d0, 0xc00002c0f8}, 0xc0000285e8?, {0xc0000240f0, 0x1, 0x1})
        /home/icio/sdk/gotip/src/cmd/go/internal/modget/get.go:314 +0x408
main.invoke(0xe371a0, {0xc0000240d0, 0x3, 0x3})
        /home/icio/sdk/gotip/src/cmd/go/main.go:225 +0x3d9
main.main()
        /home/icio/sdk/gotip/src/cmd/go/main.go:179 +0x7ce

Also fails with:

$ go version
go version go1.18.6 linux/amd64

$ go1.19 version
go version go1.19 linux/amd64
