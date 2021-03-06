# fis3-lint-csslint

[![npm version](https://badge.fury.io/js/fis3-lint-csslint.svg)](https://badge.fury.io/js/fis3-lint-csslint)  [![npm](https://img.shields.io/npm/dt/fis3-lint-csslint.svg)](http://npm-stat.com/charts.html?package=fis3-lint-csslint&author=zhangyihua&from=2016-01-01&to=2116-01-24)

基于 [csslint](https://github.com/CSSLint/csslint) 的 fis3 css linter。插件使用遵循 fis3 规则。

----

## 使用

### 安装

全局安装：

```cli
	npm install -g fis3-lint-csslint
```

安装到当前目录：

```cli
	npm install fis3-lint-csslint
```

### 配置

**example:**

```javascript
// fis-conf.js

var csslintConf = {
	ignoreFiles: ['css/myignore.css'],
	rules: {
	  'known-properties': 2
	}
};

fis.match('css/*.css', {
	lint: fis.plugin('csslint', csslintConf)
});

```

`csslintConf.rules` 是对 csslint 的规则配置。规则详细请参见[csslint rules](https://github.com/CSSLint/csslint/wiki/Rules)。

`csslintConf.ignoreFiles`： 一个数组，配置应该忽略掉的文件，数组成员为文件的匹配模式。

### 默认配置

```js
{
	"rules": {
	  "known-properties": 2,
	  "empty-rules": 1,
	  "duplicate-properties": 1
	}
}

```

默认配置规则（rules）说明：

- [know-properties] 错误的属性名。
- [empty-rules] 样式规则内容为空。
- [duplicate-properties] 属性在一条规则里重复使用。

更多规则请参见 [csslint rules](https://github.com/CSSLint/csslint/wiki/Rules)。