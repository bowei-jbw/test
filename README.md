# 1 编码风格

## 1.1 缩进 Indentation

- 1.1.1 【强制】使用 2 个空格缩进。 eslint: [`indent`](https://eslint.org/docs/rules/indent.html)

```javascript
// bad
function foo() {
∙∙∙∙let name;
}

// good
function bar() {
∙∙let name;
}
```

- 1.1.2 【强制】缩进规则：当一个新**块（block）**出现时，缩进增加 2 个空格。当一个块结束时，回到上一个层级的缩进级别。eslint: [`indent`](https://eslint.org/docs/rules/indent.html)

  > 术语解释：**块（block）**或块状结构是指类、函数、方法、控制语句或由大括号 `{}` 分隔的代码块的主体

  ```javascript
  // good
  function foo() {
  ∙∙let name;
  ∙∙if (isBar) {
  ∙∙∙∙name = 'luffy';
  ∙∙} else {
  ∙∙∙∙name = 'sabo';
  ∙∙}
  ∙∙return name;
  }
  ```

## 1.2 分号 Semicolon

- 1.2.1 【强制】使用分号。 eslint: [`semi`](https://eslint.org/docs/rules/semi.html)

  > 语句以分号结尾，可以避免 [Automatic Semicolon Insertion](https://tc39.github.io/ecma262/#sec-automatic-semicolon-insertion) 的怪异行为。[Automatic Semicolon Insertion](https://tc39.github.io/ecma262/#sec-automatic-semicolon-insertion) 是当 js 当遇到不带分号的换行时判断是否自动添加分号的机制，它在个别情况下的行为比较怪异，可能导致意想不到的效果。此外随着 js 新特性的增加，异常的情况可能变得更加复杂。因此我们统一以分号结束语句，以免受其影响，在语义上也更加明确。

  ```javascript
  // bad
  // 导致 Uncaught ReferenceError 报错
  const luke = {}
  const leia = {}
  [luke, leia].forEach(jedi => jedi.father = 'vader')

  // 导致 Uncaught TypeError 报错
  const reaction = "No! That's impossible!"
  (async function meanwhileOnTheFalcon() {
  }())

  // 函数将返回 `undefined` 而不是换行后的值
  function foo() {
    return
      'Result want to be returned'
  }

  // good
  // 所有语句以分号结尾
  const luke = {};
  const leia = {};
  [luke, leia].forEach((jedi) => {
    jedi.father = 'vader';
  });

  const reaction = "No! That's impossible!";
  (async function meanwhileOnTheFalcon() {
  }());

  function foo() {
    return 'Result want to be returned';
  }
  ```

## 1.3 逗号 Comma

- 1.3.1 【强制】用逗号分隔的多行结构，不使用行首逗号。 eslint: [`comma-style`](https://eslint.org/docs/rules/comma-style.html)

  ```javascript
  // bad
  const story = [
      once
    , upon
    , aTime
  ];

  // good
  const story = [
    once,
    upon,
    aTime,
  ];

  // bad
  const hero = {
      firstName: 'Ada'
    , lastName: 'Lovelace'
    , superPower: 'computers'
  };

  // good
  const hero = {
    firstName: 'Ada',
    lastName: 'Lovelace',
    superPower: 'computers',
  };
  ```
