# Child Mind Institute — Problematic Internet Use

[Link](https://www.kaggle.com/competitions/child-mind-institute-problematic-internet-use)


## 日本語

### 概要

子供や青少年の身体活動に基づいて、問題のあるインターネット使用のレベルを予測できますか？このコンペティションの目標は、子供の身体活動とフィットネスデータを分析して、問題のあるインターネット使用の早期兆候を特定する予測モデルを開発することです。これらのパターンを特定することで、より健康的なデジタル習慣を促進するための介入を引き起こすことができます。

### 説明

今日のデジタル時代において、子供や青少年の間で問題のあるインターネット使用は増大する懸念事項です。この問題をよりよく理解することは、うつ病や不安などの精神的健康問題に対処するために重要です。

現在、子供や青少年の問題のあるインターネット使用を測定する方法は複雑で、専門的な評価が必要です。これにより、多くの家族にとってアクセス、文化、言語の障壁が生じます。これらの制限のため、問題のあるインターネット使用は直接測定されることは少なく、代わりに若者のうつ病や不安などの問題と関連付けられます。

一方で、身体とフィットネスの測定は非常にアクセスしやすく、最小限の介入や臨床的専門知識で広く利用可能です。姿勢の悪化、不規則な食事、身体活動の減少など、過度の技術使用者に共通する身体習慣の変化があります。これらの容易に取得可能な身体フィットネス指標を、臨床的専門知識や適切な評価ツールが不足している状況で、問題のあるインターネット使用を特定するための代理として使用することを提案します。

このコンペティションでは、子供の身体活動データを分析して、問題のあるインターネットや技術使用の早期指標を検出できる予測モデルを開発することが求められます。これにより、より健康的なデジタル習慣を促進するための迅速な介入が可能になります。

あなたの仕事は、子供たちがデジタル環境を責任を持ってナビゲートできるようにするための、より健康で幸せな未来に貢献します。

##### 謝辞

このコンペティションで使用されるデータは、ニューヨーク市を拠点とする画期的な精神健康研究であるHealthy Brain Networkによって提供されました。Healthy Brain Networkでは、家族、地域のリーダー、サポーターが協力して、発達中の脳の秘密を解き明かしています。Kaggleチームからの寛大なサポートに加えて、California Department of Health Care Services (DHCS)からの財政的支援も提供されています。これはChildren and Youth Behavioral Health Initiative (CYBHI)の一環です。

#### スポンサーシップ

Dell TechnologiesとNVIDIAは、子供や青少年の精神健康支援を進めるこの協力の深い影響を認識し、Child Mind Instituteと提携できることを喜んでいます。このパートナーシップは、社会の利益のために技術を活用し、より健康で包括的な未来を促進するという私たちのコミットメントと完全に一致しています。

#### Dell Technologies

デスクトップからデータセンター、クラウドまでのAIソリューション。NVIDIAは、他の誰も解決できない課題に取り組むために加速コンピューティングを先駆けました。私たちのAIとデジタルツインの取り組みは、世界最大の産業を変革し、社会に深い影響を与えています。

### 評価

提出物は、2つの結果の一致を測定する二次加重カッパに基づいてスコアリングされます。このメトリックは通常、0（ランダムな一致）から1（完全な一致）まで変動します。偶然による一致が予想されるよりも少ない場合、このメトリックは0未満になることがあります。

二次加重カッパを計算するために、$O$、$W$、$E$の3つの行列を構築します。ここで、$N$は異なるラベルの数です。

行列$O$は$N×N$のヒストグラム行列で、$O_{i, j}$は実際の値$i$と予測値$j$を持つインスタンスの数に対応します。

行列$W$は、実際の値と予測値の二乗差に基づいて計算される$N×N$の重み行列です：

$
W_{i,j} = \frac{(i-j)^2}{(N-1)^2}
$

行列$E$は、値間に相関がないと仮定して計算される$N×N$の期待結果のヒストグラム行列です。これは、実際の結果のヒストグラムベクトルと予測結果のヒストグラムベクトルの外積として計算され、$E$と$O$が同じ合計を持つように正規化されます。

これら3つの行列から、二次加重カッパは次のように計算されます：

$
\kappa = 1 - \frac{\sum_{i,j} W_{i,j} O_{i,j}}{\sum_{i,j} W_{i,j} E_{i,j}}
$

#### 提出ファイル

テストセットの各IDに対して、対応するsii（データページで説明）を予測する必要があります。ファイルにはヘッダーが含まれており、次の形式である必要があります：

```
id,sii
000046df,0
000089ff,1
00012558,2
00017ccd,3
...
```

### コード要件

これはコードコンペティションです。
このコンペティションへの提出はノートブックを通じて行う必要があります。コミット後に「提出」ボタンがアクティブになるためには、次の条件を満たす必要があります：

- CPUノートブック <= 9時間の実行時間
- GPUノートブック <= 9時間の実行時間
- インターネットアクセス無効
- 自由に利用可能な外部データ（事前学習モデルを含む）が許可されます
- 提出ファイルはsubmission.csvと命名されなければなりません

提出方法の詳細については、コードコンペティションFAQを参照してください。提出エラーが発生している場合は、コードデバッグドキュメントを確認してください。

### Overview

Can you predict the level of problematic internet usage exhibited by children and adolescents, based on their physical activity? The goal of this competition is to develop a predictive model that analyzes children's physical activity and fitness data to identify early signs of problematic internet use. Identifying these patterns can help trigger interventions to encourage healthier digital habits.

### Description

In today’s digital age, problematic internet use among children and adolescents is a growing concern. Better understanding this issue is crucial for addressing mental health problems such as depression and anxiety.

Current methods for measuring problematic internet use in children and adolescents are often complex and require professional assessments. This creates access, cultural, and linguistic barriers for many families. Due to these limitations, problematic internet use is often not measured directly, but is instead associated with issues such as depression and anxiety in youth.

Conversely, physical & fitness measures are extremely accessible and widely available with minimal intervention or clinical expertise. Changes in physical habits, such as poorer posture, irregular diet, and reduced physical activity, are common in excessive technology users. We propose using these easily obtainable physical fitness indicators as proxies for identifying problematic internet use, especially in contexts lacking clinical expertise or suitable assessment tools.

This competition challenges you to develop a predictive model capable of analyzing children's physical activity data to detect early indicators of problematic internet and technology use. This will enable prompt interventions aimed at promoting healthier digital habits.

Your work will contribute to a healthier, happier future where children are better equipped to navigate the digital landscape responsibly.

##### Acknowledgments

The data used for this competition was provided by the Healthy Brain Network, a landmark mental health study based in New York City that will help children around the world. In the Healthy Brain Network, families, community leaders, and supporters are partnering with the Child Mind Institute to unlock the secrets of the developing brain. In addition to the generous support provided by the Kaggle team, financial support has been provided by the California Department of Health Care Services (DHCS) as part of the Children and Youth Behavioral Health Initiative (CYBHI).

#### Sponsorship

Dell Technologies and NVIDIA are thrilled to partner with the Child Mind Institute, recognizing the profound impact this collaboration will have on advancing mental health support for children and adolescents. This partnership aligns perfectly with our commitment to leveraging technology for social good and fostering a healthier, more inclusive future.

#### Dell Technologies

AI solutions from desktop to datacenter to cloud. NVIDIA pioneered accelerated computing to tackle challenges no one else can solve. Our work in AI and digital twins is transforming the world's largest industries and profoundly impacting society.

### Evaluation

Submissions are scored based on the quadratic weighted kappa, which measures the agreement between two outcomes. This metric typically varies from 0 (random agreement) to 1 (complete agreement). In the event that there is less agreement than expected by chance, the metric may go below 0.

To compute the quadratic weighted kappa, we construct three matrices, $O$
, $W$, and $E$, with $N$ the number of distinct labels.

The matrix $O$ is an $N×N$ histogram matrix such that $O_{i, j}$ corresponds to the number of instances that have an actual value $i$ and a predicted value $j$.

The matrix $W$ is an $N×N$ matrix of weights, calculated based on the squared difference between actual and predicted values:

$
W_{i,j} = \frac{(i-j)^2}{(N-1)^2}
$

The matrix $E$ is an $N×N$ histogram matrix of expected outcomes, calculated assuming that there is no correlation between values. This is calculated as the outer product between the actual histogram vector of outcomes and the predicted histogram vector, normalized such that $E$ and $O$ have the same sum.

From these three matrices, the quadratic weighted kappa is calculated as:

$
\kappa = 1 - \frac{\sum_{i,j} W_{i,j} O_{i,j}}{\sum_{i,j} W_{i,j} E_{i,j}}
$

####Submission File

For each id in the test set, you must predict the corresponding sii (described on the Data page). The file should contain a header and have the following format:

```
id,sii
000046df,0
000089ff,1
00012558,2
00017ccd,3
...
```

### Code Requirements

This is a Code Competition
Submissions to this competition must be made through Notebooks. In order for the "Submit" button to be active after a commit, the following conditions must be met:

- CPU Notebook <= 9 hours run-time
- GPU Notebook <= 9 hours run-time
- Internet access disabled
- Freely & publicly available external data is allowed, including pre-trained models
- Submission file must be named submission.csv

Please see the Code Competition FAQ for more information on how to submit. And review the code debugging doc if you are encountering submission errors.
