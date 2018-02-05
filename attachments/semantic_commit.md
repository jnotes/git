# 主义化提交(Semantic Commit Messages)

## 使用这个约定的原因:
- 自动生成修改日志
- 更清晰且有意义的Git历史记录 (例如. 忽略样式更改)

## 提交消息结构:
```bash
<type>(<scope>): <subject>

<body>

<footer>
```

## 示例:

```bash
fix(middleware): ensure Range headers adhere more closely to RFC 2616

Add one new dependency, use `range-parser` (Express dependency) to compute
range. It is more well-tested in the wild.

Fixes #2310
```

## 标题(Message subject) (首行)
首行不能大于70个字符, 第二行总是空白的并且其他行应该在80个字符以内. `<type>` 和 `<scope>` 始终是小写.

### `<type>`可用值:

* **feat** (用例的新特性，而不是构建脚本的新特性)
* **fix** (用例的Bug修复，而不是构建脚本的Bug修复)
* **docs** (对文档的更改)
* **style** (格式化，缺少分号，没有生产代码变更等；)
* **refactor** (重构生产代码，例如重命名变量)
* **test** (添加缺失测试、重构测试、无生产代码更改)
* **chore** (修改构建脚本，更新Grunt任务等；没有生产代码更改)

### 示例 `<scope>` 值:

* init
* runner
* watcher
* config
* web-server
* proxy
* etc.

`<scope>` 可以是空的 (例如. 如果更改是全局的，或者很难分配给单个组件), 在这种情况下，不需要括号. 在小的项目或插件中 `<scope>` 是空的.


## 内容(Message body)
* 使用祈使句,现在时: “change” 不是 “changed” 也不是 “changes”
* 包括改变的动机和与先前行为的对比。

For more info about message body, see:

* http://365git.tumblr.com/post/3308646748/writing-git-commit-messages
* http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html


## Message footer

### Referencing issues
Closed issues should be listed on a separate line in the footer prefixed with "Closes" keyword like this:
```bash
Closes #234
```
or in the case of multiple issues:
```bash
Closes #123, #245, #992
```
### Breaking changes

All breaking changes have to be mentioned in footer with the
description of the change, justification and migration notes.
```bash
BREAKING CHANGE:

`port-runner` command line option has changed to `runner-port`, so that it is
consistent with the configuration file syntax.

To migrate your project, change all the commands, where you use `--port-runner`
to `--runner-port`.
```

---

This document is based on [AngularJS Git Commit Msg Convention]. See the
[commit history] for examples of properly-formatted commit messages.

[AngularJS Git Commit Msg Convention]: https://docs.google.com/document/d/1QrDFcIiPjSLDn3EL15IJygNPiHORgU1_OOAqWjiDU5Y/edit#
[commit history]: https://github.com/karma-runner/karma/commits/master
