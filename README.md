# Hawkes Process for LOB modelling

## Please cite the following if you wish to use this code

1) Jain, Konark and Firoozye, Nick and Kochems, Jonathan and Treleaven, Philip, Limit Order Book Dynamics and Order Size Modelling Using Compound Hawkes Process (December 14, 2023). Available at SSRN: <https://ssrn.com/abstract=4766449> or <http://dx.doi.org/10.2139/ssrn.4766449>
2) Jain, Konark and Firoozye, Nick and Kochems, Jonathan and Treleaven, Philip, Limit Order Book Simulations: A Review (October 2023). Available at SSRN: <https://ssrn.com/abstract=4745587> or <http://dx.doi.org/10.2139/ssrn.4745587>

## Installing conda env

1) Create conda env with python dependencies

    `sh setup_dependencies.sh`

2) Activate conda env

    `conda activate hwe`

3) Download .whl file to install tick package

    Download the .whl file from <https://pypi.org/project/tick/#files> and run `pip install file-name.whl`

## MacOS arm64 users configuration

- 删除旧 uv 虚拟环境（如果有）
`rm -rf .venv`
`rm -rf ~/.cache/uv`

- 删除旧的 conda 环境（如果存在）
`conda env remove -n hwe`

- 强制用 Intel 架构，并按照 environment.yml 创建新的 conda 环境
`CONDA_SUBDIR=osx-64 conda env create -f environment.yml`

- 激活环境
`conda activate hwe`

- 固定这个环境永远使用 x86_64
`conda config --env --set subdir osx-64`

- 检查系统架构
`python -c "import platform; print(platform.platform())"`

- 下载 tick 的 x86_64 版本并安装
- 访问 <https://pypi.org/project/tick/#files> 下载适用于 macOS x86_64 的 .whl 文件
- 使用 `pip install tick-0.7.0.1-cp38-cp38-macosx_10_15_x86_64.whl` 安装下载的文件
- 验证 tick 是否正确安装 `python -c "import importlib.metadata as m; print(m.version('tick'))"`
