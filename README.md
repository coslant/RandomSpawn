<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=soft&color=0:FCAF01,50:FE2C6B,100:FC05AC&height=160&section=header&text=RandomSpawn&fontSize=60&fontColor=FFFFFF&fontAlignY=42&desc=Spigot%20%2F%20Paper%20%E2%80%A2%201.8%20%E2%86%92%201.21.11&descSize=15&descAlignY=72&animation=fadeIn" alt="RandomSpawn" width="100%" />
</p>

<p align="center">
  <a href="https://github.com/coslant/RandomSpawn/releases/latest"><img src="https://img.shields.io/github/v/release/coslant/RandomSpawn?style=for-the-badge&label=%C4%B0ndir&color=FE2C6B&logo=github" alt="Download" /></a>
  <a href="https://discord.gg/forges"><img src="https://img.shields.io/badge/Discord-Forges%20Studio-5865F2?style=for-the-badge&logo=discord&logoColor=white" alt="Discord: Forges Studio" /></a>
</p>

<p align="center">
  <a href="https://github.com/coslant/RandomSpawn/actions/workflows/build.yml"><img src="https://img.shields.io/github/actions/workflow/status/coslant/RandomSpawn/build.yml?branch=main&style=flat-square&label=build" alt="Build" /></a>
  <img src="https://img.shields.io/badge/Minecraft-1.8%20%E2%86%92%201.21.11-FCAF01?style=flat-square" alt="Minecraft 1.8 - 1.21.11" />
  <img src="https://img.shields.io/badge/Spigot%20%7C%20Paper-FE9808?style=flat-square" alt="Spigot | Paper" />
  <img src="https://img.shields.io/badge/Java-8-FD6C29?style=flat-square&logo=openjdk&logoColor=white" alt="Java 8" />
  <a href="LICENSE"><img src="https://img.shields.io/github/license/coslant/RandomSpawn?style=flat-square&color=FB0C9E&label=lisans" alt="License" /></a>
</p>

<p align="center">
  <b>Rastgele güvenli doğum ve /rtp ışınlanması.</b>
  <br>
  <sub><kbd>EN</kbd> Safe random spawns on first join and respawn, plus an /rtp command.</sub>
</p>

Yeni oyuncular haritanın rastgele bir yerinde başlar, ölünce rastgele doğar ve `/rtp` ile
istedikleri zaman ışınlanabilir. Tek jar **1.8 – 1.21.11** arası çalışır.

## ✨ Özellikler

- 🎲 İlk girişte ve yeniden doğuşta **rastgele güvenli konum**
- 🌀 **`/rtp` komutu** — bekleme süresi, geri sayım ve bekleme (cooldown) desteğiyle
- 🚶 Beklerken hareket edilirse ışınlanma iptal olur
- 🛡️ Güvenlik kontrolü: lav, ateş, kaktüs, magma, portal ve kar kuyusunun üstüne ışınlamaz
- 🌊 İsteğe bağlı olarak suyun üstüne ışınlamayı engeller
- 🔥 **Nether desteği** — tavanı olan dünyalarda aşağı doğru tarayarak hava boşluğu bulur
- ⚡ Arama **tick'lere bölünerek** yapılır; chunk yükleme sunucuyu kilitlemez
- 📏 En az uzaklık ayarı ile spawn çevresine düşmeyi engeller
- 🛏️ Yatak spawn'ı korunur (istersen zorlayabilirsin)

## 📥 Kurulum

1. [Releases](https://github.com/coslant/RandomSpawn/releases/latest) sayfasından `RandomSpawn.jar` dosyasını indir.
2. Sunucunun `plugins/` klasörüne at.
3. Sunucuyu yeniden başlat.
4. `plugins/RandomSpawn/config.yml` dosyasından merkez ve yarıçapı ayarla.

## 🎮 Komutlar

| Komut | Açıklama | Yetki |
|-------|----------|-------|
| `/rtp` | Rastgele güvenli bir yere ışınlanır | `randomspawn.rtp` |
| `/rtp <oyuncu>` | Başka bir oyuncuyu ışınlar | `randomspawn.rtp.others` |
| `/randomspawn reload` | Ayarları yeniden yükler | `randomspawn.reload` |

**Alias:** `/randomtp` · `/rastgele` · `/rs`

## 🔑 Yetkiler

| Yetki | Açıklama | Varsayılan |
|-------|----------|------------|
| `randomspawn.rtp` | `/rtp` kullanabilir | herkes |
| `randomspawn.rtp.bypass` | Bekleme süresi ve cooldown olmadan ışınlanır | op |
| `randomspawn.rtp.others` | Başkalarını ışınlayabilir | op |
| `randomspawn.reload` | Configi yeniden yükler | op |

## ⚙️ Ayarlar (config.yml)

| Anahtar | Açıklama |
|---------|----------|
| `world` | Hangi dünya (boş = ana dünya) |
| `center-x` / `center-z` | Merkez koordinatı |
| `radius` / `min-radius` | En fazla ve en az uzaklık |
| `max-attempts` | Toplam deneme sayısı |
| `attempts-per-tick` | Her tick'te kaç deneme (düşük = daha az yük) |
| `avoid-water` | Suyun üstüne ışınlamayı engelle |
| `unsafe-blocks` | Ek güvensiz bloklar |
| `nether-scan-from` / `nether-scan-to` | Nether tarama aralığı |
| `first-join` / `respawn` | İlk giriş ve yeniden doğuşta çalışsın mı |
| `override-bed` | Yatak spawn'ını yok say |
| `rtp.warmup` / `cooldown` | Bekleme süresi ve iki kullanım arası bekleme |
| `rtp.cancel-on-move` | Hareket edince iptal |
| `rtp.use-current-world` | Oyuncunun bulunduğu dünyada ışınlansın |

## 🛠️ Derleme

```bash
mvn clean package
```

Çıktı: `target/RandomSpawn.jar`

> 1.8 uyumluluğu için Java 8 hedefiyle derlenir. En sorunsuz derleme **JDK 8, 11 veya 17** iledir.

Her push'ta [GitHub Actions](https://github.com/coslant/RandomSpawn/actions/workflows/build.yml) projeyi otomatik derler; etiketlenen sürümler (`v*`) jar'ıyla birlikte [Releases](https://github.com/coslant/RandomSpawn/releases) sayfasında yayınlanır.

## 💬 Destek

- 🐛 Hata bildirimi ve öneriler için [Issues](https://github.com/coslant/RandomSpawn/issues) sekmesini kullan.
- 💬 Sorular ve destek için [Forges Studio Discord](https://discord.gg/forges) sunucusuna katıl.

## 📄 Lisans

[MIT](LICENSE) — dilediğin gibi kullan, değiştir, dağıt.

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=0:FCAF01,50:FE2C6B,100:FC05AC&height=4&section=footer" width="100%" alt="" />
  <br>
  <sub>🔥 <a href="https://github.com/coslant">coslant</a> tarafından geliştirildi · <a href="https://discord.gg/forges">Forges Studio</a></sub>
</p>
