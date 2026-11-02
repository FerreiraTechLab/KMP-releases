# KMP releases

Downloads oficiais do **KMP**, o instalador de homebrews para handhelds que distribui os pacotes por BitTorrent a partir de um catálogo assinado. [English below](#english).

> **Alfa fechada.** Estas versões são para um grupo pequeno de testadores. Espere bugs e mudanças sem aviso.

Documentação completa: <https://kpm-ferreiratechlab.web.app>

## Downloads

As versões ficam em [Releases](https://github.com/FerreiraTechLab/KMP-releases/releases).

| Aplicativo | Para quem | Arquivo |
| --- | --- | --- |
| **KMP Client** | Quem baixa e instala jogos no console | `KMP-v<versão>.zip` |
| **KMP Publisher** | Quem publica ports no catálogo | `KMP Publisher-<versão>.AppImage` (Linux), `KMP Publisher Setup <versão>.exe` (Windows), `KMP Publisher-<versão>-arm64.dmg` (Mac Apple Silicon), `KMP Publisher-<versão>.dmg` (Mac Intel) |

### KMP Client no console

Funciona em firmwares compatíveis com PortMaster em `aarch64` (DarkOS, Rocknix, AurNix e outros).

1. Extraia o ZIP e copie `KMP.sh` e a pasta `KMP/` para a pasta de Ports do cartão.
2. Abra **KMP** pelo menu Ports.

O console também semeia o que baixou (até 100 KiB/s por padrão, pausando com bateria abaixo de 30%), ajudando os próximos a baixar mais rápido.

### KMP Publisher no computador

Os instaladores ainda **não são assinados**, então o sistema avisa na primeira vez:

- **Linux:** `chmod +x "KMP Publisher-<versão>.AppImage"` e execute o arquivo.
- **Windows:** no aviso do SmartScreen, clique em **Mais informações → Executar assim mesmo**.
- **macOS:** abra o DMG, arraste o app para Aplicativos e, na primeira abertura, clique com o botão direito no app e escolha **Abrir**.

## Conferindo os arquivos

Cada release traz `SHA256SUMS.txt`. Confira antes de instalar:

```bash
sha256sum -c SHA256SUMS.txt --ignore-missing
```

No Windows (PowerShell): `Get-FileHash "KMP Publisher Setup <versão>.exe"` e compare com a linha correspondente.

## Limitações conhecidas da alfa

- Há um único nó público semeando o catálogo; se ele cair, os downloads seguem pelos consoles que já têm os jogos.
- O Publisher precisa ficar aberto até o nó público receber um pacote novo; em conexões lentas isso pode levar quase uma hora para pacotes grandes.
- A cópia opcional de pacotes grandes no Release do fork pode falhar em conexões instáveis; o envio pelo BitTorrent continua mesmo assim.

## Relatando problemas

Abra uma [issue](https://github.com/FerreiraTechLab/KMP-releases/issues) dizendo o aplicativo, a versão, o sistema ou firmware e o que aconteceu. No console, anexe o pacote de diagnóstico gerado pelo KMP.

---

## English

Official downloads of **KMP**, the homebrew installer for handhelds that distributes packages over BitTorrent from a signed catalog.

> **Closed alpha.** These builds are for a small group of testers. Expect bugs and changes without notice.

Full documentation: <https://kpm-ferreiratechlab.web.app/en/docs/>

Builds are under [Releases](https://github.com/FerreiraTechLab/KMP-releases/releases).

- **KMP Client** (`KMP-v<version>.zip`): for PortMaster-compatible `aarch64` firmwares. Copy `KMP.sh` and `KMP/` to the Ports folder and open **KMP** from the Ports menu. The console also seeds what it downloaded.
- **KMP Publisher**: AppImage for Linux, NSIS installer for Windows, and DMGs for Apple Silicon (`-arm64`) and Intel Macs. The installers are **not signed** yet: on Linux run `chmod +x` first; on Windows choose **More info → Run anyway**; on macOS right-click the app and choose **Open** the first time.

Verify downloads with `sha256sum -c SHA256SUMS.txt --ignore-missing`. Report problems in [issues](https://github.com/FerreiraTechLab/KMP-releases/issues) with the app, version, system or firmware, and what happened.
