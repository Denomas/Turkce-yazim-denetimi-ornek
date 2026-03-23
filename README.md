# Vale Turkish Örnek Proje (GitHub)

Bu proje, [vale-turkish](https://github.com/tolgakaratas/vale-turkish) entegrasyonunun nasıl çalıştığını göstermek için oluşturulmuştur.

## Yapı

```
docs/
├── tr/              ← Vale Turkish burada çalışır
│   ├── giris.md         (hatasız belge)
│   └── hatali-belge.md  (bilerek hatalı belge)
└── en/              ← Vale Turkish burada çalışmaz
    └── readme.md
```

## Entegrasyonlar

### Pre-commit

`.pre-commit-config.yaml` ile her commit'te otomatik denetim:

```yaml
repos:
  - repo: https://github.com/tolgakaratas/vale-turkish
    rev: v1.1.0
    hooks:
      - id: vale-turkish
        args: [--minAlertLevel=warning]
        files: ^docs/tr/
```

### GitHub Actions

`.github/workflows/vale.yml` dosyasında 2 farklı senaryo gösterilmektedir:

| Senaryo | Açıklama | Nasıl çalışır |
|---------|----------|---------------|
| `vale-turkish-action` | GitHub Actions composite action ile | `uses: tolgakaratas/vale-turkish@v1.1.0` |
| `vale-turkish-precommit` | Pre-commit üzerinden CI'da | `pre-commit run vale-turkish --all-files` |

Kendi ortamınıza uygun senaryoyu seçebilirsiniz.
