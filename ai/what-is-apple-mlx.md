# What Is Apple MLX

__Category: AI__

MLX, developed by Apple Machine Learning Research is an implementation of the NumPy framework designed for efficient and flexible machine learning on Apple Silicon. It uses composable function transformations for automatic differentation, automatic vectorisation, and computation graph optimisation.

MLX leverages the unified memory model available on macOS and Apple Silicon with supported device types of CPU and GPU. It supports machine learning models, LLMs, image generation, and speech recognition.

Install using pip:

```shell
pip install mlx
```

Alternatively, install using conda-forge:

```shell
conda install conda-forge:mlx
```

For a full list of generation options:

```shell
mlx_lm.generate --help
```

Hugging Face [contains models and weights](https://huggingface.co/models?library=mlx&sort=trending) that have been converted and published in MLX format.

See [MLX](https://opensource.apple.com/projects/mlx) for more details.
