---
title: エンタープライズにDevOpsを導入する
---

# エンタープライズに<br>DevOpsを導入する
## 2022/01/29

---

# アジェンダ

<div class="h-4/5 text-4xl grid grid-cols-1 content-center">
  <ul>
    <li>DevOpsとは何か</li>
    <li>よく使うツール</li>
    <li>初期に良くありそうなミス</li>
  </ul>
</div>

---
layout: intro
---

# 自己紹介

<div class="flex">
  <div class="basis-1/4">
    <img src="/profile.png" class="rounded-full px-6 py-6" />
    <div class="py-3 text-4xl text-center font-bold">WinterYukky</div>
    <div class="flex justify-around">
      <a href="https://github.com/WinterYukky" target="_blank" alt="GitHub" class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
        <mdi-github class="text-3xl" />
      </a>
      <a href="https://twitter.com/WinterYukky" target="_blank" alt="Twitter" class="text-xl icon-btn opacity-50 !border-none !hover:text-sky-500">
        <mdi-twitter class="text-3xl text-sky-500" />
      </a>
    </div>
  </div>
  <div class="basis-2/4 pl-10">
    <ul class="text-2xl">
      <li>大阪のスタートアップ所属</li>
      <li>新規事業推進室 室長</li>
      <li>好きなテクノロジー
        <ul class="text-xl">
          <li>静的型付け言語</li>
          <li>Infrastructure as Code</li>
          <li>CI / CD</li>
        </ul>
      </li>
    </ul>
  </div>
  <div class="basis-1/4 pl-10">
    <img src="/aws-certified-cloud-practitioner.png" class="rounded-full px-6" />
    <img src="/aws-certified-solutions-architect-associate.png" class="rounded-full px-6 pt-6" />
  </div>
</div>

---
layout: section
---

# DevOpsとは何か？

---

# DevOpsとは
<div class="grid grid-cols-1 content-center h-4/5">
  <div class="text-4xl italic text-center">
    開発担当と運用担当が連携・協力し、
  </div>
  <div class="text-4xl italic text-center">
    総合的に開発速度を向上させるソフトウェア開発手法
  </div>
</div>

---

# ウォーターフォール型の開発

<div class="grid justify-center content-center h-1/2">
  <img src="/ウォーターフォール.svg" />
</div>
<div class="font-medium text-3xl mb-3">特徴</div>
<ul>
  <li>順序の厳守と文書化を徹底</li>
  <li>プロセスや期間を厳格に定義</li>
  <li>変更には極端に弱いため柔軟性には欠ける</li>
</ul>

---

# アジャイル型の開発

<div class="grid grid-cols-3 h-1/2">
  <div class="justify-self-end">
    <img src="/アジャイル.svg" class="h-4/5" />
  </div>
  <div class="justify-self-center">
    <img src="/アジャイル.svg" class="h-4/5" />
  </div>
  <div class="justify-self-start">
    <img src="/アジャイル.svg" class="h-4/5" />
  </div>
</div>
<div class="font-medium text-3xl mb-3">特徴</div>
<ul>
  <li>機能毎に開発・テスト・デプロイを行う</li>
  <li>上記を繰り返すことで早期リリースを実現する</li>
  <li>変更には強いが計画の見通しには欠ける</li>
</ul>

---

# DevOps型の開発

<div class="grid grid-cols-1 content-items-center h-1/2">
  <div class="justify-self-center">
    <img src="/DevOps.svg" class="h-1/2" />
  </div>
</div>
<div class="font-medium text-3xl mb-3">特徴</div>
<ul>
  <li>アジャイルの思想を運用を含めたソフトウェア開発ライフサイクル全体に適用した手法</li>
  <li>アジャイルとは対象範囲が違う</li>
</ul>

---

# アジャイル型の開発
<div class="grid grid-cols-2 gap-6 content-center place-items-center h-3/5">
  <div class="py-10 shadow-lg rounded-lg bg-pink-500 text-center w-3/5">
    <div class="text-2xl">開発チーム</div>
    <div>
      <mdi-account-group class="text-6xl mr-1"/>
      <mdi-dev-to class="text-3xl"/>
    </div>
  </div>
  <div class="py-10 shadow-lg rounded-lg bg-sky-500 text-center w-3/5">
    <div class="text-2xl">運用チーム</div>
    <div>
      <mdi-account-group class="text-6xl mr-1"/>
      <mdi-hammer-wrench class="text-3xl"/>
    </div>
  </div>
</div>
<div class="text-2xl">
  <div v-click class="mb-3">開発チームと運用チームを組織的に分離</div>
  <div v-click class="ml-2 text-xl"><mdi-arrow-right class="mr-3"/>それぞれの担当者領域で専門的知識を用いて効率化するアプローチ</div>
  <div v-click class="ml-2 text-xl"><mdi-arrow-right class="mr-3"/>開発サイクルが早くなっても運用チームは追従できない</div>
</div>

<!-- ギャップがある -->

---

# DevOpsモデルの開発
<div class="grid grid-cols-1 gap-6 content-center place-items-center h-3/5">
  <div class="py-10 shadow-lg rounded-lg bg-purple-500 text-center w-3/5">
    <div class="text-2xl">DevOpsチーム</div>
    <div class="grid grid-cols-2 content-center place-items-center ">
      <div class="text-right w-3/5">
        <div>
          <mdi-account-group class="text-6xl mr-1"/>
          <mdi-dev-to class="text-3xl"/>
        </div>
      </div>
      <div class="text-left w-3/5">
        <div>
          <mdi-account-group class="text-6xl mr-1"/>
          <mdi-hammer-wrench class="text-3xl"/>
        </div>
      </div>
    </div>
  </div>
</div>
<div class="text-2xl">
  <div v-click class="mb-3">開発と運用で１つのチーム or 2つのチームで共同作業</div>
  <div v-click class="ml-2 text-xl"><mdi-arrow-right class="mr-3"/>開発から運用までソフトウェア開発フロー全体で効率化するアプローチ</div>
  <div v-click class="ml-2 text-xl"><mdi-arrow-right class="mr-3"/>開発者が運用まで担当するためリリースサイクルの速度が改善</div>
  <div v-click class="ml-2 text-xl"><mdi-arrow-right class="mr-3"/>開発者が自然と運用面を考慮した設計をするように</div>
</div>

---

# DevOpsの6つの原則
<ul>
  <li v-click class="my-2">
    <div class="font-black">顧客中心の活動</div>
    <div class="text-sm opacity-90 ml-4">短いフィードバックループにより、顧客の視点を理解して採り入れます。</div>
  </li>
  <li v-click class="my-2">
    <div class="font-black">目標を意識した創造</div>
    <div class="text-sm opacity-90 ml-4">各自の役割を厳格に定義するよりも、組織全体としてIT製品を組織内外の顧客に向けてどのように創造するか考えることを奨励します。</div>
  </li>
  <li v-click class="my-2">
    <div class="font-black">エンドツーエンドの責任</div>
    <div class="text-sm opacity-90 ml-4">各自が自分の役割の責任だけを負う(開発者はインフラの障害に関与せず、運用チームはコードの不具合について責任を持たない)のではなく、DevOpsではこうしたサイロを解消して、チーム全体として目的と責任を持って成果を出すことを目指します。</div>
  </li>
  <li v-click class="my-2">
    <div class="font-black">機能横断的な自律型チーム</div>
    <div class="text-sm opacity-90 ml-4">ITの生産物1つ1つについて、それを発案してから提供し、改善のサイクルを経て廃棄するところまでをカバーするために、あらゆるスキルを持ち責任を果たすチームを構築する必要があります。</div>
  </li>
  <li v-click class="my-2">
    <div class="font-black">継続的改善</div>
    <div class="text-sm opacity-90 ml-4">DevOpsを実践するチームは、常にスピードと質の向上、無駄の排除を目指します。</div>
  </li>
  <li v-click class="my-2">
    <div class="font-black">自動化できるものはすべて自動化</div>
    <div class="text-sm opacity-90 ml-4">業務のスピード、効率、有効性を向上させるためには、ITによる自動化を可能な限り活用することがきわめて重要です。そうすることでチームメンバーに余裕が生まれ、より価値ある業務に従事したり、人的エラーを削減したりすることができます。</div>
    </li>
</ul>

---

# DevOpsのフェーズ
<div class="grid grid-cols-3 gap-10 items-center h-4/5">
  <div>
    <img src="/DevOps.svg" />
  </div>
  <ul class="col-span-2 grid gap-4 grid-cols-5 items-center">
    <div class="text-xl font-bold">Plan</div>
    <div v-click class="col-span-4">
      <span class="px-1">...</span>要件定義、リリース計画
    </div>
    <div class="text-xl font-bold">Create</div>
    <div v-click class="col-span-4">
      <span class="px-1">...</span>設計、コーディング
    </div>
    <div class="text-xl font-bold">Verify</div>
    <div v-click class="col-span-4">
      <span class="px-1">...</span>テスト、パフォーマンス
    </div>
    <div class="text-xl font-bold">Package</div>
    <div v-click class="col-span-4">
      <span class="px-1">...</span>ステージング
    </div>
    <div class="text-xl font-bold">Release</div>
    <div v-click class="col-span-4">
      <span class="px-1">...</span>プロダクションへのデプロイ
    </div>
    <div class="text-xl font-bold">Configure</div>
    <div v-click class="col-span-4">
      <span class="px-1">...</span>追加インフラストラクチャのプロビジョニング
    </div>
    <div class="text-xl font-bold">Monitor</div>
    <div v-click class="col-span-4">
      <span class="px-1">...</span>メトリクスや統計の監視
    </div>
  </ul>
</div>

---
layout: section
---

# 良く使われるツール

---

# バージョン管理

<div class="grid grid-cols-3 mt-15">
  <div class="flex flex-col items-center">
    <div class="text-3xl font-bold">GitHub</div>
    <div class="h-40 grid items-center">
      <mdi-github class="text-6xl" />
    </div>
    <ul>
      <li>Dependabotの導入が容易</li>
      <li>他サービスとの連携も簡単</li>
      <li>セルフホストが可能</li>
    </ul>
  </div>
  <div class="flex flex-col items-center">
    <div class="text-3xl font-bold">GitLab</div>
    <div class="h-40 grid items-center">
      <img src="/GitLab.svg" class="h-15"/>
    </div>
    <ul>
      <li>豊富な機能</li>
      <li>無料でセルフホストが可能</li>
    </ul>
  </div>
  <div class="flex flex-col items-center">
    <div class="text-3xl font-bold">AWS CodeCommit</div>
    <div class="h-40 grid items-center">
      <img src="/AWS-CodeCommit.svg" class="h-15"/>
    </div>
    <ul>
      <li>IAMでのユーザー管理が可能</li>
      <li>IAMでIPアドレス制限が可能</li>
    </ul>
  </div>
</div>

---

# CI / CD

<div class="grid grid-cols-3 mt-15">
  <div class="flex flex-col items-center">
    <div class="text-3xl font-bold">GitHub Actions</div>
    <div class="h-40 grid grid-cols-3 items-center place-items-center">
      <mdi-github class="text-6xl" />
      <mdi-close class="text-3xl" />
      <img src="/GitHub-Actions.svg" class="h-15"/>
    </div>
    <ul>
      <li>GitHubの公式CIサービス</li>
      <li>無料でセルフホストが可能</li>
    </ul>
  </div>
  <div class="flex flex-col items-center">
    <div class="text-3xl font-bold">GitLab CI</div>
    <div class="h-40 grid grid-cols-3 items-center place-items-center">
      <img src="/GitLab.svg" class="h-15"/>
      <mdi-close class="text-3xl" />
      <img src="/GitLab-CI.svg" class="h-15"/>
    </div>
    <ul>
      <li>GitLabの公式CIサービス</li>
      <li>無料でセルフホストが可能</li>
    </ul>
  </div>
  <div class="flex flex-col items-center">
    <div class="text-3xl font-bold">AWS CodeBuild</div>
    <div class="h-40 grid grid-cols-3 items-center place-items-center">
      <img src="/AWS-CodeCommit.svg" class="h-15"/>
      <mdi-close class="text-3xl" />
      <img src="/AWS-CodeBuild.svg" class="h-15"/>
    </div>
    <ul>
      <li>CodeシリーズのCIサービス</li>
      <li>CodeCommit以外でも利用可能</li>
    </ul>
  </div>
</div>

---

# オーケストレーション

<div class="grid grid-cols-3 mt-15">
  <div class="flex flex-col items-center">
    <div class="text-3xl font-bold">Kubernetes</div>
    <div class="h-40 grid items-center">
      <mdi-kubernetes class="text-6xl text-blue-500" />
    </div>
    <ul>
      <li>OSSのコンテナオーケストレーション</li>
      <li>クラウド以外でも利用可能</li>
    </ul>
  </div>
  <div class="flex flex-col items-center">
    <div class="text-3xl font-bold">AWS ECS</div>
    <div class="h-40 grid items-center">
      <img src="/AWS-Fargate.svg" class="h-15"/>
    </div>
    <ul>
      <li>AWSのコンテナオーケストレーション</li>
      <li>Fargateタイプならクラスタ管理が不要</li>
    </ul>
  </div>
  <div class="flex flex-col items-center">
    <div class="text-3xl font-bold">AWS Lambda</div>
    <div class="h-40 grid items-center">
      <img src="/AWS-Lambda.svg" class="h-15"/>
    </div>
    <ul>
      <li>AWSのFaaS</li>
      <li>様々なAWSサービスからトリガー可能</li>
    </ul>
  </div>
</div>

---

# Infrastructure as Code

<div class="grid grid-cols-3 mt-15">
  <div class="flex flex-col items-center">
    <div class="text-3xl font-bold">Ansible</div>
    <div class="h-40 grid items-center">
      <mdi-ansible class="text-6xl text-gray-500" />
    </div>
    <ul>
      <li>VMの操作が可能</li>
      <li>YAMLで記述</li>
    </ul>
  </div>
  <div class="flex flex-col items-center">
    <div class="text-3xl font-bold">Terraform</div>
    <div class="h-40 grid items-center">
      <mdi-terraform class="text-6xl text-indigo-600" />
    </div>
    <ul>
      <li>マルチクラウド対応可能</li>
      <li>HCLで記述</li>
    </ul>
  </div>
  <div class="flex flex-col items-center">
    <div class="text-3xl font-bold"><span class="pr-2">AWS</span>CloudFormation</div>
    <div class="h-40 grid items-center">
      <img src="/AWS-CloudFormation.svg" class="h-15"/>
    </div>
    <ul>
      <li>AWSの様々なサービスに対応</li>
      <li>YAMLで記述</li>
    </ul>
  </div>
</div>

---

# モニタリング

<div class="grid grid-cols-3 mt-15">
  <div class="flex flex-col items-center">
    <div class="text-3xl font-bold">Grafana</div>
    <div class="h-40 grid items-center">
      <img src="/Grafana.svg" class="h-15"/>
    </div>
    <ul>
      <li>OSSの可視化ツール</li>
      <li>様々なデータソースをグラフで可視化</li>
    </ul>
  </div>
  <div class="flex flex-col items-center">
    <div class="text-3xl font-bold"><span class="pr-2">Amazon</span>CloudWatch</div>
    <div class="h-40 grid items-center">
      <img src="/Amazon-CloudWatch.svg" class="h-15"/>
    </div>
    <ul>
      <li>AWSのモニタリングサービス</li>
      <li>設定に応じてアクションが可能</li>
      <li>アクションにはイベント発火やアラームが可能</li>
    </ul>
  </div>
  <div class="flex flex-col items-center">
    <div class="text-3xl font-bold">AWS X-Ray</div>
    <div class="h-40 grid items-center">
      <img src="/AWS-X-Ray.svg" class="h-15"/>
    </div>
    <ul>
      <li>AWSのマイクロサービス分析サービス</li>
      <li>HTTPリクエストを計測する</li>
      <li>ボトルネックになっているサービスを特定可能</li>
    </ul>
  </div>
</div>

---
layout: section
---

# 実際に使って良かったツール

---

# 実際に使って良かったツール
<div class="grid grid-cols-2 items-center h-4/5 mx-8">
  <div class="flex flex-col items-center justify-center">
    <div class="text-3xl font-bold">AWS CDK</div>
    <div class="mt-4">
      <img src="/AWS-CDK.svg" class="h-15"/>
    </div>
  </div>
  <div>
    <ul>
      <li>AWSクラウドをプログラム言語で構築できるツール</li>
      <li>ビルドするとAWS CloudFormationを出力する</li>
      <li>TypeScript、 Java、 C#、 Pythonで記述可能</li>
      <li>簡潔に記述できてレビューしやすい</li>
      <li>CDに組込みやすい</li>
    </ul>
  </div>
</div>

---

# CloudFormationとAWS CDKについて

<div class="grid grid-cols-5 gap-6 mx-5 content-items-center h-4/5">
  <div class="col-span-2">
    <div class="text-2xl flex items-center">
      <img src="/AWS-CloudFormation.svg" class="h-9 mr-3"/>
      AWS CloudFormation
    </div>

```yml
AWSTemplateFormatVersion: "2010-09-09"
Description: A sample template
Resources:
  MyEC2Instance:
    Type: "AWS::EC2::Instance"
    Properties: 
      ImageId: "ami-xxxxxxxxxxxxxx"
      InstanceType: t2.micro
```

  </div>
  <div class="col-span-3">
    <div class="text-2xl flex items-center">
      <img src="/AWS-CDK.svg" class="h-9 mr-3" />
      AWS CDK
    </div>

```ts
import * as ec2 from 'aws-cdk-lib/aws-ec2';

export class MySampleStack extends Stack {
  constructor(scope: Construct, id: string, props?: StackProps) {
    super(scope, id, props);
    const myEC2Instance = new ec2.Instance(this, 'MyEC2Instance', {
      instanceType: 't2.micro',
      machineImage: ec2.MachineImage.genericLinux({
        'ap-northeast-1': 'ami-xxxxxxxxxxxxxx',
      });
    });
  }
}
```

  </div>
</div>

---

# 実際に使って良かったツール
<div class="grid grid-cols-2 items-center h-4/5 mx-8">
  <div class="flex flex-col items-center justify-center">
    <div class="text-3xl font-bold">GitLab CIのセルフホスト</div>
    <div class="mt-4">
      <img src="/GitLab-CI.svg" class="h-15"/>
    </div>
  </div>
  <div>
    <ul>
      <li>CIツールとして優秀</li>
      <li>公式ドキュメントのAWSでホストする手順が良かった</li>
      <li>ホストするインスタンスにロールを割り当てることで<br />IAM認証情報を外部サービスに埋め込まなくて良くなる</li>
      <li>CPUやメモリの制限が自由自在</li>
      <li>IPを固定する事でIP制限のある状況も潜り抜けれる</li>
    </ul>
  </div>
</div>

---

# 実際に使って良かったツール
<div class="grid grid-cols-2 items-center h-4/5 mx-8">
  <div class="flex flex-col items-center justify-center">
    <div class="text-3xl font-bold">tbls</div>
    <div class="mt-4">
      <img src="/tbls.svg" class="h-15"/>
    </div>
  </div>
  <div>
    <ul>
      <li>OSSのDBドキュメント生成ツール</li>
      <li>RDBドキュメント自動生成可能</li>
      <li>ドキュメントと実態の差分を取得できる</li>
      <li>差分を確認すればマイグレーション結果をテスト可能</li>
      <li>手動作業になりがちなマイグレーションの自動化支援</li>
      <li>CIに組込みやすい</li>
    </ul>
  </div>
</div>

---
layout: section
---

# 初期に良くありそうなミス

---

# インフラを意識しすぎたコードを書いてしまう

<div>課題</div>
<div class="mx-4 my-6">
  <div class="text-sm">環境を意識したコードが書けるようになった半面、それを超えて環境に依存したコードを書いてしまう</div>
  <div class="flex gap-6 justify-between mx-4 my-3">
    <div class="w-3/7">

```ts
if (process.env.NODE_ENV === 'production') {
  mail.send('xxx@example.com', { 
    message: '********'
  })
}
hoge()
fuga()
// ...and more
```

  </div>
    <div class="self-center"><mdi-arrow-right /></div>
  <div v-click class="w-3/7">

```ts
if (!process.env.DISABLE_EMAIL) {
  mail.send('xxx@example.com', { 
    message: '********'
  })
}
hoge()
fuga()
// ...and more
```

  </div>
  </div>
</div>
<div class="my-6">ポイント</div>
<div class="mx-4 text-sm">
  <ul>
    <li v-after>ロジックと環境は切り分ける</li>
    <li v-after>環境名を参照せずに設定値を参照する</li>
    <li v-after>設定値はCDで環境変数を用いて注入する</li>
  </ul>
</div>

---

# 運用やインフラに触れたことのないメンバーが苦戦する

<div>課題</div>
<div class="mx-4 my-6 h-1/5">
  <ul class="text-sm">
    <li>運用やインフラの知識を必要とするため、参画したてのメンバーが貢献しにくい</li>
    <li>マイクロサービス全体の運用を把握するのに時間がかかる</li>
  </ul>
</div>
<div class="my-6">ポイント</div>
<div class="mx-4 text-sm">
  <ul v-click>
    <li>これに関しては完璧な回答はない</li>
    <li>まずはマイクロサービス1つの運用までをこなせるようになるまで鍛える</li>
    <li>簡単な練習課題を容易して1人でこなすトレーニングが有効</li>
  </ul>
</div>

---

# さいごに

<div class="h-4/5 grid content-center">
  <ul class="mx-8 text-xl">
    <li>ツールを使いこなすことも重要だけど文化の方が優先</li>
    <li>DevOpsはプロジェクトよりプロダクトを優先</li>
    <li>DevOpsはゴールじゃなく、終わりのない継続的な改善のプロセス</li>
  </ul>
</div>

---
layout: section
---

# ご清聴ありがとうございました
