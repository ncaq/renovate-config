# renovate-config

利用側のデフォルトプリセットは`default.json`で、
実体の共有設定は`org-inherited-config.json`です。

`packageRules`は個別プリセットに分割してあり、
利用側では`ignorePresets`で無効化できます。

例:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>ncaq/renovate-config"],
  "ignorePresets": [
    "github>ncaq/renovate-config//preset/disable-dependabot-overlap"
  ]
}
```

現在の個別プリセット:

- `github>ncaq/renovate-config//preset/deps-dev-dependency-commit-scope`
- `github>ncaq/renovate-config//preset/disable-dependabot-overlap`
- `github>ncaq/renovate-config//preset/disable-node-major-update`
- `github>ncaq/renovate-config//preset/schedule-nix-flake-input-weekly`
