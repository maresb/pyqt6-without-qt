# pyqt6-without-qt

I want to be able to run [mypy](https://mypy-lang.org/) on [pre-commit.ci](https://pre-commit.ci/) to type-check PyQt6 code. However, since Qt is so large, I'm getting the error

```shell
build of https://github.com/pre-commit/mirrors-mypy:pyqt6,...@v1.9.0
for python@python3 exceeds tier max size 250MiB: 277.2MiB
```

Since all I care about are the stubs, I simply modify the wheels to remove the dependency on `PyQt6-Qt6`. Now, upon replacing `pyqt6` with `pyqt6-without-qt` in my `additional_dependencies`, I am under the quota and can run the full type checks.

(The particular project this is being used for is [Labelle](https://github.com/labelle-org/labelle).)
