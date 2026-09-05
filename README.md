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
tooling around them. Most of what I ship is Node/Express or Python, and Linux is
where I work every day rather than a line on a list.

## Projects

### [AI-GPU-Benchmark](https://github.com/PeGoPaz/AI-GPU-Benchmark)

[![CI](https://github.com/PeGoPaz/AI-GPU-Benchmark/actions/workflows/ci.yml/badge.svg)](https://github.com/PeGoPaz/AI-GPU-Benchmark/actions/workflows/ci.yml)

`Python` `PyQt6` `PyTorch` `Transformers` `PEFT` `NVML`

Desktop tool that measures AI training throughput on NVIDIA cards. Runs a real
LoRA fine-tune while polling the driver for temperature, power, VRAM and clocks,
then plots the run and reports steps/sec and steps/sec/W.

- Training and telemetry live on separate `QThread` workers, so the window stays
  responsive and a run stops cleanly at a step boundary.
- Warm-up steps are excluded from timing, and throughput comes from the steps that
  actually completed - an early stop reports its real rate, not an inflated one.
- The ML stack and NVML are stubbed in tests, so CI runs on a GPU-less runner.
  Ruff, mypy and pytest on Python 3.10 and 3.13, with tooling pinned.

### [Pro-me](https://github.com/PeGoPaz/Pro-me)

`Node.js` `Express` `MongoDB` `Mongoose` `React` `Vite`

Full-stack booking platform connecting customers with local service providers -
discovery by category, scheduling, reviews, and dashboards for both sides.

- REST API over Express with Mongoose schemas and route-level auth middleware.
- Session auth backed by a MongoDB store, so sessions survive a restart.
- Helmet, CORS, rate limiting and NoSQL injection sanitisation on by default.
- Environment-based config, deployed to Render from `render.yaml`.

## Toolbox

<pre>
  Languages ...... Python, JavaScript, Java, Bash, SQL
  Backend ........ Node.js, Express, REST APIs, session auth, Mongoose
  Frontend ....... React, Vite, React Router, Context API, axios
  Databases ...... MongoDB, PostgreSQL, MySQL
  ML / GPU ....... PyTorch, Transformers, PEFT/LoRA, mixed precision, NVML
  Testing ........ pytest, dependency stubbing, headless Qt runs
  Quality ........ ruff, mypy, pinned tooling, GitHub Actions
  Systems ........ Linux, Docker, SSH, shell scripting
</pre>

## Contact

[vladr.tech](https://vladr.tech) · [linkedin.com/in/pegopaz](https://linkedin.com/in/pegopaz) · [vl.rai@proton.me](mailto:vl.rai@proton.me)
