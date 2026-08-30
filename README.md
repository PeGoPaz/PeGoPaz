<pre>
__   ___      _   ___ ___ __  __ ___ ___   ___    _   ___ _  _  _____   __
\ \ / / |    /_\ |   \_ _|  \/  |_ _| _ \ | _ \  /_\ |_ _| \| |/ _ \ \ / /
 \ V /| |__ / _ \| |) | || |\/| || ||   / |   / / _ \ | || .` | (_) \ V /
  \_/ |____/_/ \_\___/___|_|  |_|___|_|_\ |_|_\/_/ \_\___|_|\_|\___/ \_/

  Education .... BSc Computing, Griffith College Dublin - final year
  Location ..... Dublin, Ireland
  Focus ........ Backend engineering, Linux, developer tooling
  Setup ........ CachyOS on the desktop, Arch + Hyprland on a ThinkPad
  Website ...... <a href="https://vladr.tech">vladr.tech</a>
</pre>

## About

Final-year computing student in Dublin. I build server-side applications and the
tooling around them, and I run the machines they end up on.

Most of what I ship is Node/Express or Python. I care about the parts that are
easy to skip: measurement that is actually correct, tests that run on a machine
without the hardware, CI that fails for a real reason. Linux is where I work every
day, not a line on a list.

## Projects

### [AI-GPU-Benchmark](https://github.com/PeGoPaz/AI-GPU-Benchmark)

[![CI](https://github.com/PeGoPaz/AI-GPU-Benchmark/actions/workflows/ci.yml/badge.svg)](https://github.com/PeGoPaz/AI-GPU-Benchmark/actions/workflows/ci.yml)

`Python` `PyQt6` `PyTorch` `Transformers` `PEFT` `NVML` `pandas` `matplotlib`

Desktop tool that measures AI training throughput on NVIDIA cards. It runs a real
LoRA fine-tune (TinyLlama, Qwen2.5 or Phi-2) while polling the driver for
temperature, power, VRAM, clocks, fan and PCIe link, then plots the run and
reports steps/sec and steps/sec/W.

What went into it:

- **Two `QThread` workers** - one training, one polling NVML every 250 ms - so the
  window stays responsive during a run and stops cleanly at a step boundary.
- **Correct measurement.** Warm-up steps are excluded from timing, because lazy
  weight loading and CUDA kernel compilation are real work but not steady state.
  Throughput is computed from steps that actually completed, so an early stop
  reports its real rate instead of an inflated one.
- **Honest telemetry.** An earlier version advertised a hotspot temperature NVML
  does not expose; those reads failed on every poll and always showed `N/A`.
  Replaced with two fields the driver does provide - memory temperature and
  thermal headroom - and every reading degrades to `N/A` on hardware without it.
- **CI that runs anywhere.** torch, transformers, peft and NVML are stubbed in the
  test suite, so the whole thing runs on a GitHub runner with no GPU and no
  multi-gigabyte install. Ruff, mypy and pytest on Python 3.10 and 3.13; linters
  pinned so a tooling release cannot turn CI red on its own.

### [Pro-me](https://github.com/PeGoPaz/Pro-me)

`Node.js` `Express` `MongoDB` `Mongoose` `React` `Vite`

Full-stack booking platform connecting customers with local service providers -
discovery by category, availability and scheduling, reviews, and separate
dashboards for customers and providers.

- REST API over Express with Mongoose schemas and route-level auth middleware.
- Session auth backed by a MongoDB session store, so sessions survive restarts.
- Hardened by default: Helmet, CORS, rate limiting, NoSQL injection sanitisation.
- Config through environment variables, deployed to Render from `render.yaml`.

### [BePro](https://github.com/PeGoPaz/BePro) - team project, 4 people

`React` `Express` `MongoDB` `axios`

Coursework build of a similar platform. My part was authentication and the client
API layer: login and registration with validation, an `AuthContext` that restores
the session on reload and redirects by role, the shared axios instance and dev
proxy config, and avatar upload with a photo lightbox.

### homelab

`Linux` `Docker` `RAID` `SSH`

Self-hosted services on a retired ThinkPad T430s. Two drives in a RAID1 mirror as
dedicated photo storage, Docker for everything else, key-only SSH with password
login disabled.

## Toolbox

<pre>
  Languages ...... Python, JavaScript, Java, Bash, SQL
  Backend ........ Node.js, Express, REST APIs, session auth, Mongoose
  Frontend ....... React, Vite, React Router, Context API, axios
  Databases ...... MongoDB, PostgreSQL, MySQL
  ML / GPU ....... PyTorch, Transformers, PEFT/LoRA, mixed precision, NVML
  Testing ........ pytest, dependency stubbing, headless Qt runs
  Quality ........ ruff, mypy, pinned tooling, GitHub Actions
  Systems ........ Linux, Docker, systemd, SSH, RAID, shell scripting
</pre>

## Currently

- Final year project - LLM-related, topic in progress.
- Turning the booking platform into something narrower: an Ireland-first
  marketplace for driving instructors.
- Expanding the homelab past storage into actual services.

## Contact

[vladr.tech](https://vladr.tech) · [linkedin.com/in/pegopaz](https://linkedin.com/in/pegopaz) · [vl.rai@proton.me](mailto:vl.rai@proton.me)
