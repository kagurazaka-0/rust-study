# Rustの勉強用

## 環境構築及びHello World

- 参考: [Rustの日本語ドキュメント 2.はじめる](https://doc.rust-jp.rs/the-rust-programming-language-ja/1.9/book/getting-started.html)

1. `curl https://sh.rustup.rs -sSf | sh`を実行

2. デフォルトをインストールしたいので、下が表示されたらそのままenter
```
   default host triple: x86_64-apple-darwin
     default toolchain: stable
               profile: default
  modify PATH variable: yes

1) Proceed with installation (default)
2) Customize installation
3) Cancel installation
>
```

3. 下記のいずれかを`~/.bash_profile`か`~/.zsh_profile`に追記
```bash
source $HOME/.cargo/env
# または($HOME/.cargo/envの中身が↓)
export PATH="$HOME/.cargo/bin:$PATH"
```

ちなみに最近のMacのデフォルトシェルがbashからzshになったらしいです。

僕はfishを使っているので`~/.config/fish/config.fish`に追記しました。

4. 以下を入力して保存

```rust
fn main() {
    println!("Hello, world!");
}
```

今回は`hello_world.rs`で保存しました。

5. `rustc hello_world.rs`でコンパイルし、`./hello_world`でhello world!

Rust上でhello worldができました。

## VSCodeで開発環境を整える

- 参考:[Visual Studio Code で Rust 開発を始めるには - Qiita](https://qiita.com/chikoski/items/53590914cc6aacc8916d)

1. [この拡張](https://marketplace.visualstudio.com/items?itemName=rust-lang.rust)をインストール

2. rustファイルを開くと、「Rustup not available」って怒られるので、vscodeのsetting.jsonの`rust-client.rustupPath`にrustupのpathを設定

```json
{
  "rust-client.rustupPath": "/Users/USER/.cargo/bin/rustup"
}
```

3. 「RLS not installed.Install?」って聞かれるので、Yesをクリック。
