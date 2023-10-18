- TCPとHTTPについて少し学ぶ。
- ソケットでTCP接続をリッスンする。
- 少量のHTTPリクエストを構文解析する。
- 適切なHTTPレスポンスを生成する。
- スレッドプールでサーバのスループットを強化する。

## TCPとHTTP
Webサーバーに関係するプロトコル
- HTTP(Hypertext Transfer Protocol)
- TCP(Transmission Control Protocol)

TCP
----
情報がとあるサーバから別のサーバへどう到達するかを定義するが、その情報までは定義しない

HTTP
----
リクエストとレスポンスの中身を定義することでTCPの上に成り立っている

## シングルスレッドのWebサーバーを構築する

### TCP接続をリッスンする
標準ライブラリ(std::net)を使う。

```Rust
#![allow(unused)]

use std::net::TcpListener;

fn main() {
    let listener = TcpListener::bind("127.0.0.1:7878").unwrap();

    for stream in listener.incoming() {
        let stream = stream.unwrap();

        // 接続が確立しました
        println!("Connection established!");
    }
}
```

ソケットをバインドする(???)
```Rust
TcpListener::bind("127.0.0.1:7878")
```

ソケット
----
システム間の通信を可能にするもの

通信のための端点(endpoint)

???

バインド
----
ソケットにポート番号等を割り当てる



