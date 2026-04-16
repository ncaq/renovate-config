# renovate-config

私の全てのリポジトリに自動適用される、
`org-inherited-config.json`は、
Dependabotとのコンフリクトを避けるための設定を読み込みます。

リポジトリで明示的に`github>ncaq/renovate-config`を指定して読み込まれる`default.json`は、
これを読み込むということはRenovateを優先すると判断して、
Dependabotとのコンフリクトを気にせずRenovateを最大限有効にします。

利用するには`renovate.json`に以下のように記述します。

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>ncaq/renovate-config"]
}
```

現在の個別プリセット:

- `github>ncaq/renovate-config//preset/deps-dev-dependency-commit-scope`
- `github>ncaq/renovate-config//preset/disable-node-major-update`
- `github>ncaq/renovate-config//preset/prefer-dependabot`
- `github>ncaq/renovate-config//preset/prefer-renovate`
- `github>ncaq/renovate-config//preset/schedule-nix-flake-input-weekly`

`overlap-managers.json`に、
DependabotとRenovateで担当範囲が重なるmanager一覧を定義しています。
`preset/prefer-dependabot.json`と、
`preset/prefer-renovate.json`はこの一覧から生成されます。
