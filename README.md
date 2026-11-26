# DAVE

[![Publish a Docker image (AMD64; Common X86_64 Linux Machine)](https://github.com/IOES-Lab/dave/actions/workflows/docker-amd64.yml/badge.svg)](https://github.com/IOES-Lab/dave/actions/workflows/docker-amd64.yml)
[![Publish a Docker image (ARM64; Apple Silicon)](https://github.com/IOES-Lab/dave/actions/workflows/docker-arm64v8.yml/badge.svg?branch=ros2)](https://github.com/IOES-Lab/dave/actions/workflows/docker-arm64v8.yml)

Documentation is currently at [http://dave-ros2.notion.site](http://dave-ros2.notion.site)

For contribution, do `pip3 install pre-commit && pre-commit install && pre-commit run --all-files` before commit.

# dave-src (uro-development)

## 概要

[IOES-Lab/dave](https://github.com/IOES-Lab/dave)（上流）をベースに、`uro-demo` などの独自モデルやセンサー構成を開発・検証するリポジトリです。作業用の `origin` は [koki-amakawa/dave](https://github.com/koki-amakawa/dave) です。

親リポジトリ [koki-amakawa/uro-sim-gz-harmonic](https://github.com/koki-amakawa/uro-sim-gz-harmonic)（`Gazebo_Pluctice`）が Git submodule として本リポジトリを取り込み、Docker / Docker Compose の構成、クローン手順、submodule 参照の更新手順はそちらの README にまとめています。

## 外部依存の固定

外部依存は `extras/repos/dave.jazzy.dependencies.repos` で次のコミットに固定しています。

| 依存 | URL | コミット |
| --- | --- | --- |
| dockwater | https://github.com/IOES-Lab/dockwater.git | `7e619bb9e45d19b93d5d180ed52bc512b0773398` |
| rocker | https://github.com/IOES-Lab/rocker.git | `63a5c780684cdc0a3d8a7a8ae6fd6006e43684f6` |

`extras/repos/dave.jazzy.repos` は dockwater / rocker を `main`、上流 DAVE を `ros2` に指定する別のマニフェストで、固定はしていません。

## uro-demo モデル

```text
models/dave_robot_models/
├── description/uro-demo/model.sdf
└── config/uro-demo/robot_config.py
```
