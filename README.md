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

- **Pre-commit:** `.pre-commit-config.yaml` ile her commit'te otomatik denetim
- **GitHub Actions:** `.github/workflows/vale.yml` ile CI/CD pipeline'da denetim
