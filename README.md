# README.md

# README #

LogViz: A Python logging library for colorful and styled console output.

### Owners ###
* KenCorp Inc.

### Programmer ###
* Owusu Kenneth Gyamfi [okwesi]

### Contributors ###
* No Contributors currently, but feel free to contribute!

### Contribution guidelines ###
* Use present perfect tense to comment all code. e.g., "Create a user."
* Follow PEP8 for code formatting.
* Run tests via `pytest`.

## Naming conventions
* Module and variable names: lowercase_with_underscores.
* Class names: CapWords.
* Constants: UPPERCASE_WITH_UNDERSCORES.

### Requirements ###
- Python 3.6+
- No external dependencies beyond the standard library.

### Installation ###
    pip install logviz

### Usage ###
    from logviz import logger

    if __name__ == "__main__":
        logger.debug("This is a debug message.")
        logger.info("This is an info message.")
        logger.success("This is a success message.")
        logger.warning("This is a warning message.")
        logger.error("This is an error message.")
        logger.critical("This is a critical message.")
        try:
            1/0
        except ZeroDivisionError:
            logger.exception("This is an exception message: Division by zero error occurred!")

#### Example Output ####
![FCOJt5u.md.png](https://iili.io/FCOJt5u.md.png)

### API Reference ###
- `get_logger(name: str = "logviz", level: int = logging.NOTSET) -> LogVizLogger`
- Logging methods:
  - `logger.debug(msg: str)`
  - `logger.info(msg: str)`
  - `logger.success(msg: str)`
  - `logger.warning(msg: str)`
  - `logger.error(msg: str)`
  - `logger.critical(msg: str)`
  - `logger.exception(msg: str)`

### Customization ###
To override styles, pass your own `style_map` to `get_logger`:
    import logging
    from logviz import get_logger
    from logviz.styles import LogLevelStyle, Style

    custom_styles = {
        logging.INFO: LogLevelStyle(foreground_color=Style.CYAN, bold=True),
        logging.SUCCESS: LogLevelStyle(foreground_color=Style.BRIGHT_GREEN)
    }
    logger = get_logger(name="custom", level=logging.DEBUG, style_map=custom_styles)

### Packaging & Publishing ###
1. Ensure `setup.py` and `pyproject.toml` are configured.
2. Build distributions:
    
        python setup.py sdist bdist_wheel
3. Upload to PyPI:
    
        twine upload dist/*

### Project Structure ###
    logviz/
    └── logviz/
        ├── __init__.py
        ├── defaults.py
        ├── formatters.py
        ├── logger.py
        └── styles.py

### License ###
MIT License
