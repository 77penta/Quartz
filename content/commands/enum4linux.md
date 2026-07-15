enum4linuxは、**Windowsシステムや[[Samba]]（[[SMB]]プロトコルを使用するLinuxサーバー）から情報を列挙（enumeration）するためのツール**です。
### 主な機能

enum4linuxは、Sambaツール（[[smbclient]], rpcclient, net, nmblookupなど）のラッパーとして動作し、以下の情報を取得できます：

- ユーザー一覧（userlist）
- グループとメンバー一覧
- 共有フォルダ（sharelist）
- パスワードポリシー情報
- OS情報やドメイン/ワークグループ情報
- RIDサイクリング（ユーザーIDの推測）
- Nullセッション（匿名アクセス）を利用した列挙

これにより、ターゲットのシステム構成や潜在的な脆弱性を把握できます。

### 使い方（基本例）
- 基本的な全列挙： enum4linux -a <ターゲットIP> （-aオプションでユーザー、シェア、グループ、パスワードポリシーなどを一括取得）
```
enum4linux -a <ターゲットIP>
```
- ユーザー一覧とOS情報のみ： 
```
enum4linux -U -o <ターゲットIP>
```
- 認証付きで詳細列挙（ユーザー/パスワード指定）
```
enum4linux -u "username" -p "password" -a <ターゲットIP>
```
### enum4linux-ngについて

enum4linuxの改良版で、JSON/YAML出力対応、サービス列挙追加、SMBバージョン自動検知など機能が強化されています。 Kaliでsudo apt install enum4linux-ng、またはGitHub（cddmp/enum4linux-ng）から入手。 使い方は似ていて、enum4linux-ng -A \<IP> で全列挙可能です。

```
enum4linux-ng -a [target ip]
enum4linux-ng # 使い方の確認
enum4linux-ng -a -u admin -p password1 [target ip]
```
