# [StyleGAN](https://arxiv.org/abs/1812.04948)
StyleGANは，PGGANをベースとした高解像度かつ本質の高い画像を生成できるGAN．PGGANよりも高レベルな特徴を扱うことができるようになった．人物画像を例にすると，大局的な属性(顔の輪郭や髪型など)から局所的な属性(シワや肌質など)まで制御できるようになった．PGGANのネットワーク構造と比較し異なる点は大きく3つ．
- 潜在変数zから潜在空間wへの非線形変換．
- AdaINの導入による大局的なスタイルの生成．
- ノイズマップによる局所的なスタイルの生成．

![StyleGAN_model](./images/StyleGAN_model.png)

※余談
StyleGAN2, StyleGAN2-ADAなど年々改良モデルが提案されている．
- StyleGAN2：AdaINの代わりに畳み込み層(CNN)の結合荷重(weight)を正規化することでアーティファクトの除去に成功した．また段階的な学習法の代わりにskip connectionを持つ階層的なGeneratorを用いることでモード崩壊の抑制と画像品質を向上させた．
- StyleGAN2-ADA：少ないデータでも学習を大幅に安定させるAdaptive Discriminator Augmentation(ADA)を導入した．Data AugmentationによりDiscriminatorの過学習を抑制するとともに，Generatorには生成画像にノイズが反映されないように学習することに成功している．

---
### 出力結果
<center><video src="./outputs/movie.mp4" autoplay muted loop></video><p>顔画像データに対する補間結果</p></center>

---
### 参考文献
[1] "A Style-Based Generator Architecture for Generative Adversarial Networks," Tero Karras, Samuli Laine, Timo Aila, CVPR2019, 
[arXiv:1812.04948](https://arxiv.org/abs/1812.04948).

[2] Karras, T., Laine, S., Aittala, M., Hellsten, J., Lehtinen, J., & Aila, T. "Analyzing and improving the image quality of stylegan," In Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (pp. 8110-8119), [arXiv:1912.04958v2](https://arxiv.org/abs/1912.04958v2).