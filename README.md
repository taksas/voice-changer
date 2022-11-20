Voice Changer Trainer and Player Container（ROHAN4600対応鬼畜版）
----
# 概要
w-okadaさんが作成したアプリケーションのレコーダー機能に、ROHAN4600（ROHANコーパス）録音機能を実装しました。
それ以外のアプリケーションは全く同じです。
ITAコーパスの500文に飽き足らないやべー方は是非ROHANコーパスの4600文に挑戦してみてください！！！！！！！！！！！！！！！！

----
# ほんとの概要
AIを使ったリアルタイムボイスチェンジャー[MMVC](https://github.com/isletennos/MMVC_Trainer)のヘルパーアプリケーションです。

MMVCで必要となる一連の作業（トレーニング用の音声の録音、トレーニング、ボイスチェンジャ）をお手軽に実行できます。
![image](https://user-images.githubusercontent.com/48346627/201169523-836e0f9e-2aca-4023-887c-52ecc219bcca.png)


Dockerを前提としたアプリケーションですが、Github PagesとGoogle Colaboratory上での実行も可能です。（Google Colaboratoryの制約により使用感が一部悪いです。）
![image](https://user-images.githubusercontent.com/48346627/201169876-36c33af9-f2d4-4746-9ddb-21186b94f6fc.png)

このアプリケーションを用いることで、以下のことを簡単に行うことができます。

- MMVCトレーニング用の音声録音 (GithubPages (Docker不要))
- MMVCのモデルのトレーニング (Dockerを強く推奨、Colabでも可)
- MMVCモデルを用いたリアルタイムボイスチェンジャー（Docker推奨、Colabでも可）
  - リアルタイム話者切り替え
  - CPU/GPU切り替え
  - リアルタイム/ニアリアルタイム声質変換


本アプリケーションのリアルタイムボイスチェンジャーは、サーバ・クライアント構成で動きます。MMVCのサーバを別のPC上で動かすことで、ゲーム実況など他の負荷の高い処理への影響を抑えながら動かすことができます。（MacのChromeからも利用できます！！）
![image](https://user-images.githubusercontent.com/48346627/201170195-88114174-0237-4610-b828-4fe08fe212e9.png)


# 使用方法

詳細な使用方法等は[wiki](https://github.com/w-okada/voice-changer/wiki)をご参照ください。


## トレーニング用音声録音アプリ

MMVCトレーニング用の音声を簡単に録音できるアプリです。
Github Pages上で実行できるため、Dockerの準備は不要です。

[録音アプリ on Github Pages](https://w-okada.github.io/voice-changer/)

録音したデータは、ブラウザ上に保存されます。外部に一切漏れることはありません。

詳細な使用方法は[wiki](https://github.com/w-okada/voice-changer/wiki/020_%E9%9F%B3%E5%A3%B0%E9%8C%B2%E9%9F%B3)をご覧ください。


## トレーニング用アプリ
MMVCのトレーニングを行うアプリです。
Dockerでの実行を強く推奨します。

詳細な使用方法等は[wiki](https://github.com/w-okada/voice-changer/wiki/030_%E3%83%88%E3%83%AC%E3%83%BC%E3%83%8B%E3%83%B3%E3%82%B0)をご参照ください。

Colaboratoryでの実行を行う場合は、次のノートから実行できます。
- [Colab ノート](https://github.com/w-okada/voice-changer/blob/master/MMVCTrainerFrontendDemo.ipynb)

Colaboratoryで実行する場合は、Colabの制約により途中切断が発生する可能性があります。Web上では各種対策が示されていますので、必要に応じて各自でご対応をお願いします。また、途中切断に備え、こまめなモデルのダウンロードをお勧めします。

## ボイスチェンジャーアプリ
Dockerでの使用を推奨します。一部ユーザ体験が劣化しますが、次のノートでColaboratoryでの実行も可能です。
- [簡単バージョン](https://github.com/w-okada/voice-changer/blob/master/VoiceChangerDemo_Simple.ipynb): 事前設定なしでColabから実行できます。 
- [詳細バージョン](https://github.com/w-okada/voice-changer/blob/master/VoiceChangerDemo.ipynb): Google Driveと連携してモデルを読み込むことができます。

[説明動画](https://twitter.com/DannadoriYellow/status/1564897136999022592)

動画との差分

- サーバの起動完了のメッセージは、「Debuggerほにゃらら」ではなく「Application startup complete.」です。
- プロキシにアクセスする際に、index.htmlを追加する必要はありません。

詳細な使用方法等は[wiki](https://github.com/w-okada/voice-changer/wiki/040_%E3%83%9C%E3%82%A4%E3%82%B9%E3%83%81%E3%82%A7%E3%83%B3%E3%82%B8%E3%83%A3%E3%83%BC)をご参照ください。

# デモ動画
## リアルタイム性

GPUを使用すると100msec強の遅延で変換することが可能です。

https://user-images.githubusercontent.com/48346627/199807082-9d2ca75b-3a05-463d-b32e-14e663603626.mp4


CPUでも最近のであればそれなりの速度で変換可能。

https://user-images.githubusercontent.com/48346627/199855821-596f0874-8f69-4354-b226-4a755e9763bc.mp4


古いCPU( i7-4770)だと、1000msecくらいかかってしまう。

# Misc
## 簡易デモ(soft-vc)
soft-vcを用いたボイスチェンジャです。

[コラボのノート](https://github.com/w-okada/voice-changer/blob/master/SoftVcDemo.ipynb)

[説明動画](https://user-images.githubusercontent.com/48346627/191019809-e7ae7c86-4b44-45f3-9dc3-3dc668992db4.mp4
)



# Acknowledgments
- 立ちずんだもん素材：https://seiga.nicovideo.jp/seiga/im10792934
- いらすとや：https://www.irasutoya.com/
