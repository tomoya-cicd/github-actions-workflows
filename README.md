# github-actions-workflows

# Reusable GitHub Actions Workflows

このリポジトリには、複数プロジェクトで再利用可能なCI/CDワークフローが含まれています。

## 📦 利用可能なワークフロー

### 1. Flutter CI/CD (`flutter-cicd.yml`)
- iOS、Android、macOS、Web の全プラットフォーム対応
- TestFlight、Google Play、Cloudflare Pagesへの自動デプロイ
- テスト、Lint、ビルド、デプロイの完全パイプライン

### 2. Python CI/CD (`python-cicd.yml`)
- テスト、Lint、カバレッジレポート
- Docker/Podman対応
- サーバーへの自動デプロイ

### 3. iOS/macOS CI/CD (`ios-cicd.yml`)
- Xcode ビルド・テスト
- TestFlight 自動デプロイ
- CocoaPods/Carthage 対応

### 4. Container CI/CD (`container-cicd.yml`)
- Docker/Podman 自動検出
- マルチプラットフォームビルド
- Docker Hub、GitHub Container Registry対応
- Trivy セキュリティスキャン

### 5. Web CI/CD (`web-cicd.yml`)
- React、Vue、Next.js、Nuxt、Svelte、Astro など対応
- Cloudflare、Vercel、Netlify、Firebase、GitHub Pages 対応
- E2Eテスト、Playwrightサポート

## 🚀 使い方

各プロジェクトの `.github/workflows/` に以下のようなファイルを作成：

### Flutter プロジェクト例

\`\`\`yaml
name: CI/CD

on:
  push:
    branches: [main]

jobs:
  build:
    uses: <username>/github-actions-workflows/.github/workflows/flutter-cicd.yml@main
    with:
      flutter-version: '3.27.1'
      build-ios: true
      build-android: true
      deploy-web: true
      environment: 'production'
    secrets:
      CLOUDFLARE_API_TOKEN: \${{ secrets.CLOUDFLARE_API_TOKEN }}
\`\`\`

## 📝 セットアップ済み

- ✅ Mac Studio M3 Ultra セルフホストランナー
- ✅ GitHub Student 特典活用
- ✅ セルフホストランナー課金延期対応

## 🔧 カスタマイズ

各ワークフローは `inputs` と `secrets` でカスタマイズ可能です。
詳細は各ワークフローファイルを参照してください。

