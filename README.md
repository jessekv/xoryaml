# xoryaml

Yet Another YAML library for Python ;)

```python
print(
    xoryaml.dumps(
        {
            "name": "xoryaml",
            "released": datetime.datetime.now(datetime.timezone.utc),
        }
    )
)
# ---
# name: xoryaml
# released: "2025-03-08T17:01:14.569027Z"
```


## Why?

I wanted a memory-safe and reasonably fast YAML library that could handle
`datetime` types. It takes inspiration (as well as a bit of the test suite)
from [orjson](https://github.com/ijl/orjson).

In order to keep the interface to native code as simple as possible, I have
implemented part of the interface in Python. Not sure if this is a bad idea, but
it seems to work fine? Let me know if otherwise.

## Thanks

This project would not be possible without:

- [pyo3](https://pyo3.rs/): Rust-python interop
- [yaml-rust2](https://github.com/ethiraric/yaml-rust2): Pure Rust YAML impl
- [orjson](https://github.com/ijl/orjson): Parts of test suite
- [ryaml](https://github.com/emmatyping/ryaml): Parts of test suite
- [speedate (pydantic)](https://github.com/pydantic/speedate): Date formatting


## Dev install
- Install [uv](https://docs.astral.sh/uv/getting-started/installation/)
- Install maturin: `uv tool install maturin`
- Make a venv `uv venv`
- Activate the venv `source .venv/bin/activate`
- Build and install `uv pip install -e '.[bench]'`
- Optional: build release `maturin develop --release`
- Run tests `pytest`

## Run tests on all supported versions of python locally

- Install tox: `uv tool install tox --with tox-uv`
- Run: `tox`
