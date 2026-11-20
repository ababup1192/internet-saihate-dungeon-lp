# assets/sfx

このフォルダの `.wav` は手で置いた録音ではなく、`make render-all` が `src/render/SfxRender.flix` から
生成する成果物です。音を変えたいときは `.wav` を直接編集せず、次のどちらかを直して
`make render-all` し直してください。

**例外は `applause.wav` だけ**（リザルト画面の拍手）。これは録音素材で、bake は触りません。
噪音の合成では拍手の質感（無数の手の反射）が出なかったため、ここだけサンプリング音源です。

- 出典: "Applause" — Blender Foundation, [OpenGameArt](https://opengameart.org/content/applause), CC-BY 3.0
- 加工: 22050Hz モノラルへ変換し、末尾 0.5 秒を先頭へクロスフェードしてループ化
- **CC-BY のため、ゲームを配るときはクレジット（Blender Foundation）を README 等に書くこと**

`relicGet.wav`（アーティファクトの入手のジングル）も render-all の外。採用した WAV が正で、描いた台本は消した（2026-10-18）。

- 音量・高さ・長さ … `assets/internet_dungeon.sfxtune.json`（Studio のフォームからも触れます）
- 音そのものの組み立て … `src/render/SfxRender.flix` の合成レシピ

BGM（`bgmDay` / `bgmNode` など）の音量だけは鳴らしながら効くので、`sfxtune.json` を保存すれば
焼き直さずに変わります。

どの出来事でどれが鳴るかは `src/Sfx.flix`、一覧は `README.md` の「音」の節にあります。
フェーズ 1 の音はすべて仮で、パズル・会話・戦闘の音が増えるたびにここへ足していきます。
