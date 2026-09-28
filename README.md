# test_deploy

A minimal smoke-test repo for a Docker + Flask deployment flow — not a
real application. It exists to verify that a container builds and serves
traffic correctly, separate from any larger project's dependencies.

## Contents

```
app.py         Single-route Flask app ("Hello from Flask!" at "/")
Dockerfile     python:3.11-slim, installs requirements.txt, exposes 8080
requirements.txt
```

## Run it

```bash
docker build -t test_deploy .
docker run -p 8080:8080 test_deploy
```

Then visit `http://localhost:8080/`.

Or without Docker:

```bash
pip install -r requirements.txt
python app.py
```

## Related repos

Created right after [`deploy_enam`](https://github.com/MJTheGreat3/deploy_enam)
in the same window as the other `enam_*` repos, this looks like a
throwaway sandbox used to check the container deployment mechanics in
isolation — the app itself has no ENAM-specific code.
