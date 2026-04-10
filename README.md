# spank-mic

**Microphone-based fork of [taigrr/spank](https://github.com/taigrr/spank) — works on ANY Mac!**

The original [spank](https://github.com/taigrr/spank) detects slaps via the Apple Silicon accelerometer, but only supports M1 Pro+ / M2+ chips. This fork replaces the accelerometer with **microphone input**, so it works on any Mac (including base M1, Intel Macs, etc.) — and doesn't require `sudo`.

---

## English

### What is this?

spank-mic listens to your MacBook's microphone for loud transient sounds (slaps, hits, claps) and plays funny audio responses. It features adaptive noise floor detection, so it adjusts to your environment automatically.

### Requirements

- macOS (any Mac with a microphone)
- [PortAudio](https://formulae.brew.sh/formula/portaudio): `brew install portaudio`
- [Go 1.21+](https://go.dev/) (only if building from source): `brew install go`

### Installation

**Download pre-built binary:**

Check the [Releases](https://github.com/mrfeixiang/spank-mic/releases) page.

**Build from source:**

```bash
git clone https://github.com/mrfeixiang/spank-mic.git
cd spank-mic
brew install portaudio pkg-config
go build -o spank-mic .
sudo cp spank-mic /usr/local/bin/
```

### Usage

```bash
# Default mode — plays "ow!" sounds
spank-mic

# Sexy mode — intensity escalates with slap frequency
spank-mic --sexy

# Halo mode — video game death sounds
spank-mic --halo

# Custom sounds — use your own MP3 files
spank-mic -c /path/to/mp3s

# Adjust sensitivity (lower = more sensitive, default 0.15)
spank-mic --min-amplitude 0.08

# Fast mode — shorter cooldown, higher sensitivity
spank-mic --fast

# Scale volume by slap intensity
spank-mic --volume-scaling
```

### Differences from original spank

| | [spank](https://github.com/taigrr/spank) | spank-mic |
|---|---|---|
| Sensor | Accelerometer (IOKit HID) | Microphone (PortAudio) |
| Requires sudo | Yes | No |
| Chip requirement | M1 Pro+ / M2+ | Any Mac |
| Detection | STA/LTA + CUSUM vibration analysis | RMS + peak transient with adaptive noise floor |

---

## 中文

### 这是什么？

spank-mic 通过 MacBook 的麦克风监听响亮的瞬态声音（拍打、敲击、鼓掌），然后播放搞笑的音频回应。它具有自适应噪声基底检测功能，会自动适应你的环境噪声。

**原项目 [taigrr/spank](https://github.com/taigrr/spank) 使用加速度计检测拍打，但仅支持 M1 Pro+ / M2+ 芯片。本分支改用麦克风输入，适用于所有 Mac（包括基础版 M1、Intel Mac 等），且不需要 `sudo` 权限。**

### 系统要求

- macOS（任何有麦克风的 Mac）
- [PortAudio](https://formulae.brew.sh/formula/portaudio)：`brew install portaudio`
- [Go 1.21+](https://go.dev/)（仅从源码构建时需要）：`brew install go`

### 安装

```bash
git clone https://github.com/mrfeixiang/spank-mic.git
cd spank-mic
brew install portaudio pkg-config
go build -o spank-mic .
sudo cp spank-mic /usr/local/bin/
```

### 使用方法

```bash
# 默认模式 — 播放"哎呦"音效
spank-mic

# 性感模式 — 拍打越频繁，声音越激烈
spank-mic --sexy

# 光环模式 — 游戏死亡音效
spank-mic --halo

# 自定义音效 — 使用你自己的 MP3 文件
spank-mic -c /path/to/mp3s

# 调节灵敏度（数值越低越敏感，默认 0.15）
spank-mic --min-amplitude 0.08
```

---

## 한국어

### 이것은 무엇인가요?

spank-mic는 MacBook의 마이크를 통해 큰 순간 소리(때리기, 두드리기, 박수)를 감지하고 재미있는 오디오 반응을 재생합니다. 적응형 노이즈 플로어 감지 기능이 있어 주변 환경에 자동으로 적응합니다.

**원본 프로젝트 [taigrr/spank](https://github.com/taigrr/spank)은 가속도계를 사용하여 때리기를 감지하지만 M1 Pro+ / M2+ 칩만 지원합니다. 이 포크는 마이크 입력으로 대체하여 모든 Mac(기본 M1, Intel Mac 포함)에서 작동하며, `sudo`가 필요하지 않습니다.**

### 시스템 요구사항

- macOS (마이크가 있는 모든 Mac)
- [PortAudio](https://formulae.brew.sh/formula/portaudio): `brew install portaudio`
- [Go 1.21+](https://go.dev/) (소스에서 빌드할 때만 필요): `brew install go`

### 설치

```bash
git clone https://github.com/mrfeixiang/spank-mic.git
cd spank-mic
brew install portaudio pkg-config
go build -o spank-mic .
sudo cp spank-mic /usr/local/bin/
```

### 사용법

```bash
# 기본 모드 — "아야!" 소리 재생
spank-mic

# 섹시 모드 — 때리는 빈도에 따라 강도 상승
spank-mic --sexy

# 헤일로 모드 — 게임 사망 사운드
spank-mic --halo

# 커스텀 사운드 — 자신의 MP3 파일 사용
spank-mic -c /path/to/mp3s

# 감도 조절 (낮을수록 민감, 기본값 0.15)
spank-mic --min-amplitude 0.08
```

---

## Credits / 致谢 / 크레딧

This project is a fork of [taigrr/spank](https://github.com/taigrr/spank) by [@taigrr](https://github.com/taigrr). All audio assets and the core playback/escalation logic come from the original project. Thank you for the amazing and fun idea!

本项目是 [@taigrr](https://github.com/taigrr) 的 [taigrr/spank](https://github.com/taigrr/spank) 的分支。所有音频资源和核心播放/升级逻辑均来自原项目。感谢原作者的精彩创意！

이 프로젝트는 [@taigrr](https://github.com/taigrr)의 [taigrr/spank](https://github.com/taigrr/spank) 포크입니다. 모든 오디오 에셋과 핵심 재생/에스컬레이션 로직은 원본 프로젝트에서 가져왔습니다. 멋진 아이디어에 감사드립니다!

## License / 许可证 / 라이선스

MIT — Same as the original project.
