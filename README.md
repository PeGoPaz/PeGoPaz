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

[![CI](https://github.com/PeGoPaz/Pro-me/actions/workflows/ci.yml/badge.svg)](https://github.com/PeGoPaz/Pro-me/actions/workflows/ci.yml)

`Node.js` `Express 5` `MongoDB` `Mongoose` `React 19` `Vite` `Cloudinary`

Marketplace for finding a driving instructor in Ireland. The RSA register says
who is approved to teach; Pro.me helps learners choose between them.

- Reference data for all 26 counties and 62 driving test centres, imported from
  the RSA's own register; search ranks verified instructors first and never by
  self-reported lesson counts.
- Reviews only from a learner whose lesson the instructor confirmed and whose
  date has passed. Moving a confirmed lesson sends it back for confirmation, so
  a lesson cannot be moved into the past to unlock a review.
- Each instructor's typical reply time: the median time to answer a lesson
  request, with requests they ignore counted against them, so ignoring them
  cannot make anyone look quick.
- Photo uploads checked by their bytes rather than their name and re-encoded,
  which strips the GPS location a phone writes into them; the 12-photo gallery
  limit is one conditional update, so two uploads at once cannot both get past it.
- EU Digital Services Act moderation: anyone can report content, no report
  closes without a statement of reasons, the author of a hidden review is told
  why, and the admin area counts the figures for the yearly transparency report.
- Session auth in MongoDB, a strict CSP and a login rate limit that counts only
  failed attempts - the first version signed people out after five page loads.
  Integration tests run against a real MongoDB.

### [property-template](https://github.com/PeGoPaz/property-template)

[![CI](https://github.com/PeGoPaz/property-template/actions/workflows/ci.yml/badge.svg)](https://github.com/PeGoPaz/property-template/actions/workflows/ci.yml)

`Python` `JavaScript` `GitHub Actions` `GitHub Pages`

The code behind a client's holiday-rental site, turned into a template: a site
for a similar property is set up by editing data files, not HTML.

- Every page is generated from a property config, a reviews file and one text
  file per language by a build that uses only Python's standard library.
- The build refuses to ship mistakes: overlapping price seasons, a translation
  missing a key, a review scored above its platform's scale or a link to a
  script that does not exist all stop it with a message saying which.
- Availability is merged from every platform's iCal feed; if one feed fails
  nothing is written, so a missing platform cannot reopen booked dates.
- CI tests, builds and deploys, and every six hours rebuilds with fresh
  availability without a commit; script and style links carry a content hash
  so a deploy never mixes old and new files.
- Works from the keyboard and with a screen reader: the booking calendar is one
  tab stop with arrow keys between days, the gallery says which photo is shown,
  and a form error is tied to the field it is about.
- A strict content security policy with no inline styles, sent as headers and
  repeated in a `<meta>` tag for GitHub Pages, which ignores headers; a test
  fails if the two copies drift apart.

## Toolbox

<pre>
  Languages ...... Python, JavaScript, C++, Java, Bash, SQL
  Backend ........ Node.js, Express, REST APIs, session auth, Mongoose
  Frontend ....... React, Vite, React Router, Context API, axios
  Databases ...... MongoDB, PostgreSQL, MySQL
  ML / GPU ....... PyTorch, Transformers, PEFT/LoRA, QLoRA, mixed precision, NVML
  Testing ........ pytest, Hypothesis, node:test, MongoDB integration tests, ASan/UBSan/TSan
  Quality ........ ruff, strict mypy, coverage floors, pinned tooling, GitHub Actions
  Systems ........ Linux, Docker, Prometheus, Grafana, SSH, shell scripting
</pre>

## Contact

[vladr.tech](https://vladr.tech) · [linkedin.com/in/pegopaz](https://linkedin.com/in/pegopaz) · [vl.rai@proton.me](mailto:vl.rai@proton.me)
