Copy of [Geir Arne Hjelle's](https://github.com/gahjelle/) [Advent of Code template](https://github.com/gahjelle/template-aoc-python), modified for my workflow 
# Advent of Code Python Template for Copier

This template creates scaffolding for one day of [Advent of Code](https://adventofcode.com/). It includes tests and can download your personal input data if you have [`advent-of-code-data`](https://pypi.org/project/advent-of-code-data/) installed.

> **Note:** You need at least [version 6](https://copier.readthedocs.io/en/latest/changelog/#600-2022-05-15) of Copier to use this template.

> **Note:** [Version 8](https://copier.readthedocs.io/en/stable/changelog/#v800-2023-06-04) of Copier changed how to work with subcommands. The commands below assume that you're running Copier v8.1.0 or higher.

## Quick Start

The first time you use this template you should make sure that you have [Copier](https://copier.readthedocs.io/) installed and optionally `advent-of-code-data` as well. You can install these with pipx and pip:

```console
$ pipx install copier
$ python -m pip install advent-of-code-data
```

Note that `advent-of-code-data` requires a small bit of [setup](https://github.com/wimglenn/advent-of-code-wim/issues/1) where you find and specify your personal Advent of Code session ID. Once you have Copier on your system, you can create Advent of Code solution templates as follows:

```console
$ copier copy --trust gh:gahjelle/template-aoc-python advent_of_code/
```

The `copy` command will copy files from the template. The `--trust` flag is needed to run the script that downloads your personal data.

This will ask you about which **year** and **day** you want to template. You can also provide a puzzle name which will be used as part of the directory name and the comments within your files.

The files are copied into a subdirectory of the `advent_of_code/` directory on your computer. You can change `advent_of_code/` to any other name you want.


## Scripting

You can also use Copier as part of a script. The [documentation](https://copier.readthedocs.io/en/stable/api/) shows how to call Copier as part of a Python script.

On the command line, you can use `-d` to provide answers to questions instead of answering them interactively. On Bash (and possibly other shells), the following will set up all directories for the 2023 event inside of your `aoc/` directory:

```console
$ for day in {01..25}; do
>     copier copy --trust gh:gahjelle/template-aoc-python -d year=2023 -d day=$day -d puzzle_name="" -d puzzle_dir=$day aoc/
> done
```

If you're using Powershell on Windows, you can use something like this instead:

```
for ($day = 1; $day -le 25; $day++) {
    $day_str = "{0:00}" -f $day
    copier copy --trust gh:gahjelle/template-aoc-python -d year=2023 -d day=$day_str -d puzzle_name="" -d puzzle_dir=$day_str aoc/
}
```

After running this, you'll have 25 subdirectories within `aoc/2023/` with templates for solving each day of Advent of Code with Python.


## Examples

See https://github.com/gahjelle/advent_of_code/tree/main/python for examples using the template. My tutorial, [Advent of Code: Solving Your Puzzles With Python](https://realpython.com/python-advent-of-code/), explains the reasoning behind the template and shows a few examples of using it to solve puzzles.


## Credits
All based on [Geir Arne Hjelle's](https://github.com/gahjelle/) [Advent of Code template](https://github.com/gahjelle/template-aoc-python), modified for my workflow 
Thanks to [Matt Gregory](https://github.com/grovduck) for helping to [debug](https://github.com/gahjelle/template-aoc-python/issues/1) this recipe for Windows and creating the Powershell script to create a full year of templates.

And a huge thanks to [Eric Wastl](https://twitter.com/ericwastl/) for creating the wonderful [Advent of Code](https://adventofcode.com/).
