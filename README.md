# renovate-config

## 自動適用される設定

`org-inherited-config.json`は私の全てのリポジトリに自動適用される設定です。

この`org-inherited-config.json`はDependabotとのコンフリクトを避けるための設定を読み込みます。

## 明示的に読み込む設定

リポジトリで明示的に`github>ncaq/renovate-config`を指定して読み込むと、
`default.json`が使われます。

明示的に読み込むということはRenovateを優先すると判断して、
Dependabotとのコンフリクトを気にせずRenovateを最大限有効にします。

この設定を利用するには`renovate.json`に以下のように記述します。

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>ncaq/renovate-config"]
}
```

## 現在の個別プリセット

- `github>ncaq/renovate-config//preset/base`
- `github>ncaq/renovate-config//preset/deps-dev-dependency-commit-scope`
- `github>ncaq/renovate-config//preset/disable-node-major-update`
- `github>ncaq/renovate-config//preset/prefer-dependabot`
- `github>ncaq/renovate-config//preset/prefer-renovate`
- `github>ncaq/renovate-config//preset/schedule-nix-flake-input-weekly`

`overlap-managers.json`に、
DependabotとRenovateで担当範囲が重なるmanager一覧を定義しています。

`preset/prefer-dependabot.json`と、
`preset/prefer-renovate.json`は、
この一覧データから`nix fmt`によって機械的に生成されます。
