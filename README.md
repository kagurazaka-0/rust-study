# Rustの勉強用

以下の内容は[Qiitaの記事](https://qiita.com/katsuya_U/items/c420728ddb9b53768a06)と同等

## 環境構築及びHello World

- 参考: [Rustの日本語ドキュメント 2.はじめる](https://doc.rust-jp.rs/the-rust-programming-language-ja/1.9/book/getting-started.html)

① `curl https://sh.rustup.rs -sSf | sh`を実行

② デフォルトをインストールしたいので、下が表示されたらそのままenter

```
1) Proceed with installation (default)
2) Customize installation
3) Cancel installation
>
```

③ 下記のいずれかを`~/.bash_profile`か`~/.zsh_profile`に追記

```bash
source $HOME/.cargo/env
# または($HOME/.cargo/envの中身が↓)
export PATH="$HOME/.cargo/bin:$PATH"
```

ちなみに最近のMacはデフォルトシェルがbashからzshになったらしいです。
僕はfishを使っているので`~/.config/fish/config.fish`に追記しました。

④ 以下を入力して保存

```rust
fn main() {
    println!("Hello, world!");
}
```
今回は`hello_world.rs`で保存しました。

⑤ `rustc hello_world.rs`でコンパイルし、`./hello_world`で実行

Rust上でhello worldができました。

## VSCodeで開発環境を整える

- 参考:[Visual Studio Code で Rust 開発を始めるには - Qiita](https://qiita.com/chikoski/items/53590914cc6aacc8916d)

① [この拡張](https://marketplace.visualstudio.com/items?itemName=rust-lang.rust)をインストール

② rustファイルを開くと、「Rustup not available」って怒られるので、vscodeのsetting.jsonの`rust-client.rustupPath`にrustupのpathを設定

```json
{
  "rust-client.rustupPath": "/Users/USER/.cargo/bin/rustup"
}
```

③ 「RLS not installed.Install?」って聞かれるので、Yesをクリック。
