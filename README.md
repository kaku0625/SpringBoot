# 管理メニューシステム（Spring Boot）

Spring Boot を用いて作成した、管理メニュー機能を中心とした Web アプリケーションです。  
画面表示から登録処理までの一連の流れを通して、Spring Boot / MVC アーキテクチャの理解を目的としています。

---

## システム概要

### 機能概要
- 管理メニュー画面表示
- 各機能画面への遷移
- データ登録・更新処理
- 入力チェック（バリデーション）

---

## 技術スタック

| 項目 | 技術 |
|-----|------|
| 言語 | Java |
| フレームワーク | Spring Boot |
| Web | Spring MVC |
| テンプレート | Thymeleaf |
| ORM | Spring Data JPA |
| データベース | MySQL |
| ビルド | Maven |
| バージョン管理 | Git / GitHub |

---

## アーキテクチャ

┌───────────────────────────────────────────┐
│ Thymeleaf (View) │
├───────────────────────────────────────────┤
│ Controller (Spring MVC) │
│ @Controller / @PostMapping │
├───────────────────────────────────────────┤
│ Service (Business Logic) │
│ @Service │
├───────────────────────────────────────────┤
│ Repository (Data Access) │
│ Spring Data JPA │
├───────────────────────────────────────────┤
│ Database │
└───────────────────────────────────────────┘

---

## ディレクトリ構成

SpringBoot/
├── pom.xml # Maven設定ファイル
├── src/main/
│ ├── java/com/example/demo/
│ │ ├── controller/ # コントローラクラス
│ │ ├── service/ # サービスクラス
│ │ ├── repository/ # リポジトリ（JPA）
│ │ ├── entity/ # エンティティクラス
│ │ └── form/ # フォームクラス
│ ├── resources/
│ │ ├── templates/ # Thymeleafテンプレート
│ │ ├── static/ # CSS / JS
│ │ └── application.properties # アプリ設定
│ └── webapp/
├── ManagementSpringBoot.mp4 # 管理メニュー画面 動作動画

---

## 画面イメージ

管理メニュー画面の動作を以下の動画で確認できます。

- ManagementSpringBoot.mp4

---

## 学習ポイント

- Spring Boot プロジェクト構成の理解
- Controller / Service / Repository の役割分離
- フォーム送信から画面遷移までの処理フロー
- Thymeleaf を用いた画面表示
- MVC アーキテクチャに基づく開発

---

## セットアップ手順

### 1. 前提条件
- JDK 17（または 11 以上）
- Maven
- MySQL

### 2. 起動方法

```bash
mvn spring-boot:run

3. アクセス

ブラウザで以下にアクセスします。
http://localhost:8080/

工夫した点
MySQLデータベース連携の実装

本プロジェクトでは、Spring Boot と MySQL を連携させ、
画面操作とデータベース処理が一連の流れで動作するように実装しました。

・Spring Data JPA を利用し、SQL を直接記述せずにデータ操作を実現

・Entity クラスとテーブル構造を対応させ、保守性を意識した設計

・Repository / Service / Controller の役割分離を徹底し、
ビジネスロジックが画面処理に依存しない構成とした

・application.properties による接続情報の外部設定で、
環境変更に柔軟に対応できるよう配慮

この実装により、登録・更新・表示といった基本的な CRUD 処理を
MySQL データベースと連携して行えるようになりました。
