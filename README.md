# react-eslint使用及其配置

### 1.在项目中安装 ESLint 作为 devDependency
      npm install -D eslint

### 2.在根目录下生成.eslintrc配置文件(可以选择js、yaml、json)
      npx eslint --init

### 3. 安装插件
      npm install -D eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react

### 4. 修改配置文件
```
{
	"extends": [
		"eslint:recommended",
		"plugin:import/errors",
		"plugin:react/recommended",
		"plugin:jsx-a11y/recommended"
	],
	"plugins": ["react", "import", "jsx-a11y"],
	"rules": {
		"react/prop-types": 0,
		"indent": ["error", 2],
		"linebreak-style": 1,
		"quotes": ["error", "double"]
	},
	"parserOptions": {
		"ecmaVersion": 2021,
		"sourceType": "module",
		"ecmaFeatures": {
		"jsx": true
		}
	},
	"env": {
		"es6": true,
		"browser": true,
		"node": true
	},
	"settings": {
		"react": {
		"version": "detect"
		}
	}
}

```
“extends”和“ plugins”：通过在 extends 属性中添加文件名，可以继承其配置，而“plugin”作为 ESLint 的扩展，可以执行多种功能。
`import-plugin` 将帮助我们识别导入和导出时的常见问题；
`jsx-a11y` 将捕获关于可访问性的错误；
`react` 插件是关于 React 中使用的代码实践,告知settings字段去检查package.json中的react版本，而不是直接将react的版本通过硬编码的方式写死。
`rules`：用于配置规则，可以看到所有可以使用的规则 https://eslint.org/docs/rules/，可以设置三种不同类型的规则错误级别：
"off"或0：关闭规则。
"warn"或1：使用规则作为警告
"error"或2：使用规则作为错误

