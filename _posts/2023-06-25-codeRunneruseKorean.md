---
title: vscode Code Runner 한글 깨짐 오류 해결
author: ha
date: 2023-06-25 20:30:00 +0900
categories: [Editor/IDE, VSCode]
tags: [Editor/IDE, VSCode, Code Runner, setting]
render_with_liquid: false
img_path: /assets/img/20230625/
---

- `code runner 톱니바퀴` 누른뒤, `json 편집(setting.json)` 마지막 단에 아래의 설정 추가

```json
"code-runner.runInTerminal": true
```

![CodeRunnerSetting](CodeRunnerSetting.png)

- 잘 나온다
  ![CodeRunnerSetting2](CodeRunnerSetting2.png)
