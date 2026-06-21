<div align="center">

<img src="https://raw.githubusercontent.com/TAKT-OS/.github/main/assets/takt-os-banner.svg" alt="TAKT OS — Industrial cycle-based RTOS for ESP32" width="100%"/>

<br/>

**Open-source industrial real-time framework for Espressif ESP32**

[![Documentation](https://img.shields.io/badge/docs-GitHub%20Pages-38bdf8?style=for-the-badge&logo=readthedocs&logoColor=white)](https://takt-os.github.io/Takt-OS/)
[![Main repo](https://img.shields.io/badge/repo-Takt--OS-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/TAKT-OS/Takt-OS)
[![License](https://img.shields.io/badge/license-Apache%202.0-22c55e?style=for-the-badge&logo=apache&logoColor=white)](https://github.com/TAKT-OS/Takt-OS/blob/main/LICENSE)
[![ESP-IDF](https://img.shields.io/badge/ESP--IDF-5.0%2B-e7352c?style=for-the-badge&logo=espressif&logoColor=white)](https://github.com/espressif/esp-idf)

<br/>

[Documentation](https://takt-os.github.io/Takt-OS/) · [Releases](https://github.com/TAKT-OS/Takt-OS/releases) · [Wiki](https://github.com/TAKT-OS/Takt-OS/wiki) · [Issues](https://github.com/TAKT-OS/Takt-OS/issues) · [Contributing](https://github.com/TAKT-OS/Takt-OS/blob/main/CONTRIBUTING.md)

</div>

---

## What we build

**TAKT OS** layers a **PLC-style scan cycle** on top of ESP-IDF and FreeRTOS. Every **takt** *(German: beat, cycle)*, the kernel walks registered modules in a **fixed order** — predictable timing for Modbus, sensors, relays, telemetry, and industrial control.

| | Typical FreeRTOS app | TAKT OS |
|---|----------------------|---------|
| Work unit | Preemptive tasks | `IModule` in fixed scan order |
| Timing | Best-effort priorities | Deterministic sequence per takt |
| Sweet spot | General multitasking | Field devices, PLC-style logic |
| Platform | ESP-IDF | ESP-IDF + TAKT kernel |

ESP-IDF still owns hardware, WiFi/BLE, flash, and OTA. TAKT OS owns **your application logic**.

---

## Repositories

| Repository | Description |
|------------|-------------|
| [**Takt-OS**](https://github.com/TAKT-OS/Takt-OS) | Core framework — kernel, drivers, middleware, examples, docs |
| [**Takt-OS Wiki**](https://github.com/TAKT-OS/Takt-OS/wiki) | Architecture notes, guides, and navigation |

---

## Stack at a glance

```
┌─────────────────────────────────────────────┐
│  Your modules (Modbus, sensors, logic…)     │
├─────────────────────────────────────────────┤
│  TAKT kernel · EventBus · TimerManager      │
├─────────────────────────────────────────────┤
│  Drivers · Middleware · Services · Recovery │
├─────────────────────────────────────────────┤
│  ESP-IDF · FreeRTOS · ESP32 / S3 / C3       │
└─────────────────────────────────────────────┘
```

**Kernel:** static / dynamic / background modules · event bus · software timers · overrun detection · diagnostics  
**Industrial stack:** GPIO/UART/ADC · Modbus RTU · WiFi/MQTT/HTTP · OTA · remote config · BLE/WiFi/UART recovery

---

## Get started

```bash
git clone https://github.com/TAKT-OS/Takt-OS.git
cd Takt-OS
# ESP-IDF or PlatformIO — see docs
```

→ [**Quick start**](https://takt-os.github.io/Takt-OS/getting-started/) · [**PlatformIO guide**](https://takt-os.github.io/Takt-OS/platformio_vscode/) · [**Architecture**](https://takt-os.github.io/Takt-OS/architecture/)

---

## Community

Contributions, issues, and field feedback are welcome.

[![CI](https://img.shields.io/github/actions/workflow/status/TAKT-OS/Takt-OS/ci.yml?branch=main&style=flat-square&label=CI&logo=githubactions&logoColor=white)](https://github.com/TAKT-OS/Takt-OS/actions)
[![Release](https://img.shields.io/github/v/release/TAKT-OS/Takt-OS?style=flat-square&logo=github&label=Release)](https://github.com/TAKT-OS/Takt-OS/releases)
[![PRs welcome](https://img.shields.io/badge/PRs-welcome-8b5cf6?style=flat-square&logo=github&logoColor=white)](https://github.com/TAKT-OS/Takt-OS/blob/main/CONTRIBUTING.md)

---

<div align="center">

**Maintained by [Masyukov Pavel](mailto:p.masyukov@gmail.com)** · Apache 2.0

<sub>Organization profile · <a href="https://github.com/TAKT-OS">github.com/TAKT-OS</a></sub>

</div>
