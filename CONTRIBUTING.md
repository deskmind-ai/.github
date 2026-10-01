# Contributing to DeskMind · 为得心做贡献

These guidelines apply to every repository in [deskmind-ai](https://github.com/deskmind-ai). Each repository adds its
own setup and test commands in its `CONTRIBUTING.md`.

本规范适用于 deskmind-ai 下的所有仓库；各仓库的 `CONTRIBUTING.md` 另外写明本仓库的环境搭建和测试命令。

## Ways to help · 参与方式

| | | Repository |
|---|---|---|
| Add a desktop task and its grader · 贡献一个桌面任务和评分器 | lowest barrier, highest value · 门槛最低、价值最高 | [bench](https://github.com/deskmind-ai/bench) |
| Submit your agent's bench results · 提交你的 agent 成绩 | added to the reference results · 收录进参考成绩 | [bench](https://github.com/deskmind-ai/bench) |
| Support another app or platform · 适配新的应用或平台 | Windows, Linux, browsers, Office | [hands](https://github.com/deskmind-ai/hands) |
| Better grounding · 更准的视觉定位 | models, data, evals · 模型、数据、评测 | [eyes](https://github.com/deskmind-ai/eyes) |
| Faster, better calibrated decisions · 更快、把握更准的决策 | serving, training, calibration · 部署、训练、校准 | [brain](https://github.com/deskmind-ai/brain) |
| Docs, translations, examples · 文档、翻译、示例 | English and 中文 · 中英文 | any · 任意仓库 |

Start with issues labelled **good first issue**. Each one says which file to change and what "done" looks like.

从带 **good first issue** 标签的 issue 开始，每个都写明了要改哪个文件、怎样算完成。

## Principles · 原则

1. **Evidence over opinion.** A change that affects model behaviour comes with before/after numbers on a probe set or
   a bench run.
   **用数据说话。** 影响模型行为的改动，要附上检测集或 bench 上改动前后的结果。
2. **Local first and private by default.** Never commit real user data, screenshots of your own apps, credentials, tokens or raw desktop traces; redact identifying paths and values but keep enough structure to reproduce.
   Keep them in a git-ignored `private/` directory.
   **本地优先、默认保护隐私。** 绝不提交真实用户数据、你自己应用的截图、密钥、令牌或原始桌面轨迹；可识别身份的路径和值请脱敏，但保留足以复现的结构；这些都放在不提交的 `private/` 目录。
3. **Honest results.** Report where we lose as clearly as where we win.
   **成绩要诚实。** 输在哪里，和赢在哪里一样写清楚。
4. **Small, focused PRs.** One change per pull request, and match the surrounding style.
   **PR 小而专注。** 一个 PR 只做一件事，风格与周围代码一致。

## Where to report · 在哪里报告

- **Project direction, cross-stack setup, unclear ownership, reproduction reports:** [deskmind](https://github.com/deskmind-ai/deskmind/issues).
  **项目方向、跨组件环境、归属不明的问题、复现报告：** 提交到 deskmind。
- **A bug isolated to one component:** that repository's tracker ([brain](https://github.com/deskmind-ai/brain/issues), [eyes](https://github.com/deskmind-ai/eyes/issues), [hands](https://github.com/deskmind-ai/hands/issues), [bench](https://github.com/deskmind-ai/bench/issues), [app](https://github.com/deskmind-ai/app/issues)).
  **已定位到单个组件的 bug：** 提交到对应仓库。
- **A change spanning repositories:** one coordinating issue in deskmind, linked to focused component issues or PRs.
  **跨仓库的改动：** 在 deskmind 开一个协调 issue，再链接到各组件的 issue 或 PR。
- **Questions and design discussion:** [Discussions](https://github.com/deskmind-ai/deskmind/discussions).
  **提问与设计讨论：** 去 Discussions。

Search first. If a report is moved, link the old and new locations instead of opening an unlinked duplicate.
先搜索已有 issue；被转移的报告请在新旧位置互相链接，不要另开无关联的重复 issue。

## Bug reports · 问题报告

Include · 请包含：
1. The smallest goal or request that reproduces it, with synthetic data and a disposable folder. · 能复现问题的最小目标或请求，使用虚构数据和临时文件夹。
2. Exact source revisions and model revision/quantization. · 准确的源码版本、模型版本和量化方式。
3. Hardware, macOS version, app versions, locale and display scaling where relevant. · 硬件、macOS 版本、相关应用版本、语言和显示缩放。
4. Expected versus actual final state, and how often it reproduces. · 预期与实际的最终状态，以及复现频率。
5. For desktop runs: the permitted apps and folder, whether projection, vision mode or remote escalation was used, and whether the final state differs from what the agent reported. · 桌面运行还要写明允许的应用和文件夹、是否用了投影/视觉模式/远程升级，以及最终状态是否与 agent 报告的不同。

## Benchmarks and reproductions · 评测与复现

Failed replications are as useful as successful ones. Record the track (Brain, Eyes, end-to-end, deployment speed); immutable source/model/data revisions and suite version; hardware, OS, runtime, quantization and decoding; repeats, retries, limits, routing and one-pass/two-pass setting; numerator/denominator with every attempted run and exclusion; and what the timing covers (inference, request, or full task).
复现失败和成功一样有价值。请记录：评测方向（Brain、Eyes、端到端、部署速度）；源码、模型、数据的固定版本和套件版本；硬件、系统、运行时、量化与解码；重复次数、重试、限制、路由、单次/两次推理；带分子分母的结果，包括所有尝试和排除项；以及耗时指的是推理、请求还是整项任务。

Compare only matched conditions: keep GPU and MLX runs, standalone models and routers, and different harness versions apart. A mock or oracle run checks wiring; it is not a model score. Never post sealed test items or data you may not redistribute.
只比较条件一致的结果：GPU 与 MLX、单模型与路由、不同 harness 版本分开报告。mock 或 oracle 运行只验证接线，不算模型成绩。不要公开密封测试题或无权再分发的数据。

## Conduct and security · 行为准则与安全

- Be kind; see [CODE_OF_CONDUCT.md](https://github.com/deskmind-ai/.github/blob/main/CODE_OF_CONDUCT.md). 友善交流，见行为准则。
- Report vulnerabilities privately, as described in [SECURITY.md](https://github.com/deskmind-ai/.github/blob/main/SECURITY.md). 安全问题请私下报告。

Contributions are licensed under each repository's licence (Apache-2.0 for code).

贡献内容按所在仓库的许可发布，代码为 Apache-2.0。
