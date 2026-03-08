# OpenClue Homebrew Tap

> [!WARNING]
> OpenClue is currently in experimental mode.
> It is not suitable for production use.
> Use at your own risk.
> Please read `RISK_NOTICE.txt` included in the respective release bundles before use.

<p align="center">
	<img src="assets/oclue_logo.png" alt="OpenClue Logo" width="420" />
</p>

OpenClue (`oclue`) ist ein Unix-nativer AI-CLI-Runner fuer echte Shell-Workflows.
Die Idee: schnelle, agentische Hilfe im Terminal, ohne Black-Box-Gefuehl und ohne Fullscreen-TUI-Zwang.

Dieses Repository ist der oeffentliche Distributionspunkt fuer OpenClue:
- Homebrew Cask (`Casks/`)
- GitHub Release-Artefakte (Binaries)

## Warum OpenClue

OpenClue fuehlt sich wie ein normales CLI-Tool an, aber mit deutlich mehr Assistenz im Alltag:
- Agentische Unterstuetzung fuer reale Aufgaben statt nur Prompt rein, Text raus.
- Klar sichtbare Plaene, Status und Audit-Signale statt intransparenter Ausfuehrung.
- Funktioniert fuer Pair-Shelling, Background-Jobs und CI-Flows.
- Deterministische Sicherheitsgrenzen: Ausfuehrung wird durch Policy/Permissions geregelt, nicht durch Modelltext.
- Sauberer Unix-Stream-Vertrag (`stdout` Payload, Steuerung getrennt), damit Pipes robust bleiben.

Kurz: OpenClue hilft dir schneller voranzukommen, ohne die Kontrolle ueber deine Shell abzugeben.

## Installation (macOS)

```bash
brew tap juangamnik/openclue
brew install --cask openclue
```

Danach sind beide Kommandos verfuegbar:
- `oclue`
- `openclue`

## Linux Artefakte

Releases in diesem Repo enthalten Linux-Pakete als:
- `.deb`
- `.rpm`
- `.tar.gz`

## App-Icon

Das App-Icon ist bewusst kompakt und klar gehalten, damit es in Dock, Launcher und Finder auch in kleinen Groessen gut lesbar bleibt.

<img src="assets/app_icon.png" alt="OpenClue App Icon" width="128" height="128" />

## Zum Logo

Das OpenClue-Logo mit dem Honeyguide steht fuer das Produktprinzip:
AI fuehrt dich zu einer guten Spur, aber Entscheidungen und Ausfuehrung bleiben sichtbar und unter deiner Kontrolle.

## Repositories

- Release/Tap: `juangamnik/homebrew-openclue`
- Source (Code, CI, Release-Workflow): `juangamnik/openclue`

## Maintainer Notes

Operational guidance is documented in [docs/maintainers.md](docs/maintainers.md).
