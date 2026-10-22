<pre>
__   ___      _   ___ ___ __  __ ___ ___   ___    _   ___ _  _  _____   __
\ \ / / |    /_\ |   \_ _|  \/  |_ _| _ \ | _ \  /_\ |_ _| \| |/ _ \ \ / /
 \ V /| |__ / _ \| |) | || |\/| || ||   / |   / / _ \ | || .` | (_) \ V /
  \_/ |____/_/ \_\___/___|_|  |_|___|_|_\ |_|_\/_/ \_\___|_|\_|\___/ \_/

  Education .... BSc Computing, Griffith College Dublin - final year
  Location ..... Dublin, Ireland
  Focus ........ Backend engineering, Linux, developer tooling
  Website ...... <a href="https://vladr.tech">vladr.tech</a>
</pre>

## About

Final-year computing student in Dublin. I build server-side applications and the
tooling around them. Most of what I ship is Node/Express or Python, and Linux is
where I work every day rather than a line on a list.

## Projects

### [AI-GPU-Benchmark](https://github.com/PeGoPaz/AI-GPU-Benchmark)

[![CI](https://github.com/PeGoPaz/AI-GPU-Benchmark/actions/workflows/ci.yml/badge.svg)](https://github.com/PeGoPaz/AI-GPU-Benchmark/actions/workflows/ci.yml)
[![Release](https://img.shields.io/github/v/release/PeGoPaz/AI-GPU-Benchmark)](https://github.com/PeGoPaz/AI-GPU-Benchmark/releases)

`Python` `C++17` `PyTorch` `PEFT` `PyQt6` `NVML` `Prometheus` `Docker`

Benchmarks NVIDIA GPUs on a real LoRA fine-tune. It started as a way to tell
whether my deshrouded RTX 4070 Ti actually ran cooler, and shipped as 0.1.0 with
a desktop dashboard, a headless mode for servers and an optional C++ sampler.

- Throughput as tokens/sec and MFU against a peak computed from the card's
  architecture, SM count and clock; energy per training step from NVML's
  counter; a thermal model fitted to the temperature curve.
- A C++17 extension samples board power at 500 Hz on its own thread outside the
  GIL, through a lock-free ring buffer, tested under ASan, UBSan and TSan.
- `--repeat` with outlier rejection, `--sweep` ranked by a Pareto front of speed
  against efficiency, a Prometheus endpoint with a Grafana dashboard, a SQLite
  history of every run and a CUDA container image.
- Strict mypy and about 500 tests with Hypothesis and a 93% coverage floor, all
  without a GPU; CI on Linux, Windows and macOS, releases built from version tags.

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
  Languages ...... Python, JavaScript, C++, Java, Bash, SQL
  Backend ........ Node.js, Express, REST APIs, session auth, Mongoose
  Frontend ....... React, Vite, React Router, Context API, axios
  Databases ...... MongoDB, PostgreSQL, MySQL
  ML / GPU ....... PyTorch, Transformers, PEFT/LoRA, QLoRA, mixed precision, NVML
  Testing ........ pytest, Hypothesis, dependency stubbing, ASan/UBSan/TSan
  Quality ........ ruff, strict mypy, coverage floors, pinned tooling, GitHub Actions
  Systems ........ Linux, Docker, Prometheus, Grafana, SSH, shell scripting
</pre>

## Contact

[vladr.tech](https://vladr.tech) · [linkedin.com/in/pegopaz](https://linkedin.com/in/pegopaz) · [vl.rai@proton.me](mailto:vl.rai@proton.me)
