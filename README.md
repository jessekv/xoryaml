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
it seems to work fine? Let me know otherwise ;)

## Thanks

This project would not be possible without:

- [pyo3](https://pyo3.rs/): Rust-python interop
- [yaml-rust2](https://github.com/ethiraric/yaml-rust2): Pure Rust YAML impl
- [orjson](https://github.com/ijl/orjson): Test suite
- [speedate (pydantic)](https://github.com/pydantic/speedate): Date formatting


## Tests

- Install tox: `uv tool install tox --with tox-uv`
- Run: `tox`
