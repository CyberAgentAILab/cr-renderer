# CR Renderer

This Python package renders document data in [the crello dataset](https://huggingface.co/datasets/cyberagent/crello). This is a standalone renderer package from the [OpenCOLE](https://github.com/CyberAgentAILab/OpenCOLE) project.

## Install

```bash
pip install git+https://github.com/CyberAgentAILab/cr-renderer
```

See `pyproject.toml` for the detail of dependency requirements.

## Usage

For Crello dataset revision 5.0.0:

```python
import datasets
from cr_renderer import CrelloV5Renderer

dataset = datasets.load_dataset(
    "cyberagent/crello", revision="5.0.0", split="train")
renderer = CrelloV5Renderer(dataset.features)
for example in dataset:
    image_bytes = renderer.render(example)
```

For Crello dataset revision 4.0.0:

```python
import datasets
from cr_renderer import CrelloV4Renderer

dataset = datasets.load_dataset(
    "cyberagent/crello", revision="4.0.0", split="train")
renderer = CrelloV4Renderer(dataset.features)
for example in dataset:
    image_bytes = renderer.render(example)
```

## Development

The package is managed by [uv](https://github.com/astral-sh/uv). To start development:

```bash
git clone https://github.com/CyberAgentAILab/cr-renderer.git
cd cr-renderer
uv sync
```
