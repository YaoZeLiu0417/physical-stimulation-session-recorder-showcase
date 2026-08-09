# Physical Stimulation Intervention Session Companion

**Public showcase · 研究会话原型公开展示**

A documentation-only showcase of a privacy-conscious research-session prototype. The prototype brings controlled entry, brief daily context, browser-local audiovisual recording, stepwise structured responses, local response export, and completion confirmation into one guided workflow.

本项目用于展示受控研究会话的流程与隐私边界。目前仍是研究原型，尚未替代由研究人员监督的正式会话流程，也不构成临床产品或自动化居家干预系统。

**Private synthetic demo — access available on request.**

![Synthetic walkthrough of the public demonstration](assets/workflow-demo.gif)

[Static workflow image / 静态流程图](assets/workflow-demo-static.webp)

## My Contributions · 我的工作

- Designed the six-stage operational journey and the explicit gates between access, recording, response, export, and completion.
- Implemented the browser-local recording experience, including device readiness, local WebM saving, playback checks, and explicit save confirmation.
- Built the session-scoped JSON + Excel export flow and the associated state-cleanup and privacy boundaries.
- Created a separate synthetic demonstration and a fail-closed public-asset audit so the interaction can be shown without publishing study-specific content.
- Produced the bilingual walkthrough and visual documentation for research and engineering review.

## Two Related, Distinct Flows · 两套相关但不同的流程

### Six-stage operational prototype · 六阶段正式原型

This is the intended structure of a supervised research session. Study-specific measurement content is deliberately omitted from this showcase.

| Stage | Purpose | Data boundary |
| --- | --- | --- |
| **1. Controlled entry / 受控进入** | Establish the authorized session context | Access details are managed separately |
| **2. Daily context / 当日状态** | Record the minimum context needed for the session | Values remain session-scoped until local export |
| **3. Browser-local recording / 本地音视频** | Record and verify camera video plus microphone audio | Media stays in Chrome and is saved by the user |
| **4. Stepwise structured responses / 分步作答** | Present one required response step at a time | Study-specific content is not included here |
| **5. Local response package / 本地资料包** | Generate equivalent JSON and Excel records in one ZIP | The user downloads and checks the package locally |
| **6. Completion confirmation / 完成确认** | Confirm both local outcomes and close the active flow | Application-owned session state is cleared |

### Five-state synthetic public demo · 五状态公开合成演示

The public-facing demonstration is intentionally smaller. It preserves the interaction pattern while replacing operational content with invented feedback prompts and synthetic values.

| Demo state | What it demonstrates |
| --- | --- |
| **Overview / 流程概览** | Neutral explanation of the synthetic session |
| **Local capture / 本地录制** | Device readiness, recording, local save, and no-save fallback |
| **Synthetic reflection / 合成反馈** | Four invented sliders used only to demonstrate progression |
| **Synthetic download / 合成下载** | A locally downloaded JSON + Excel ZIP containing invented values |
| **Confirmation / 完成确认** | A clear terminal state and an explicit restart action |

The five states above describe the application state machine. The screenshots show smaller user-interface actions within those states; they do not represent additional operational stages.

## Browser-local Recording · 浏览器本地录制

![Synthetic local-recording walkthrough](assets/local-recording.gif)

[Static recorder image / 静态录制图](assets/local-recording-static.webp)

The current desktop Chrome workflow provides camera and microphone readiness, a stable preview, a recording timer, local playback, and explicit save confirmation.

- **Demo mode:** short recordings are held in browser memory until the user downloads the WebM.
- **Long-session mode:** recording chunks are written directly to a user-selected local file and finalized on a clean stop.
- In both modes, media bytes remain in Chrome; the Streamlit application has no media-upload path.

Interrupted or unfinished files may be incomplete. A checked confirmation records the user's verification; it is not an automatic inspection of the local file system.

## Synthetic Response and Export · 合成作答与导出

![Invented response sliders used in the synthetic demonstration](assets/step-07-synthetic-feedback.webp)

The synthetic demo uses four invented interaction questions. Their only purpose is to demonstrate focused controls, progression, local export, and completion without reproducing study-specific measurement content.

![Synthetic JSON and Excel package download](assets/step-08-local-zip-download.webp)

Synthetic response values are held in transient Streamlit session memory while one ZIP is generated. The ZIP contains equivalent JSON and Excel representations and is saved through a user-controlled browser download. The synthetic demo does not write those values or the cached ZIP to durable server storage.

## Privacy Boundary · 隐私边界

- Camera and microphone bytes remain in the browser and are saved only through a user-controlled local action.
- Synthetic response values enter transient server-side session memory only to build the local response package.
- Public screenshots and animations use generated media, invented responses, and no participant identifiers.
- This public showcase contains documentation and sanitized visual assets, not application source, credentials, or participant records.
- The current showcase asset set has passed its file-shape, content, URL, and embedded-metadata audit.

> **Release boundary:** Operational source code and study-specific materials are outside the scope of this public showcase and must remain access-restricted. A public release should be described as privacy-safe only after repository visibility and anonymous access have been independently verified.

## Current Status · 当前状态

- **Research prototype / 研究原型:** active development and evaluation.
- **Operational use / 正式使用:** supervised research procedures remain authoritative.
- **Public evidence / 公开证据:** synthetic interaction, local recording behavior, local export, and privacy-boundary documentation.
- **Not claimed / 不作声明:** clinical effectiveness, unsupervised deployment readiness, or automatic verification that a local file was saved correctly.

![Synthetic completion state](assets/step-09-confirmation.webp)

