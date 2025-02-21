---
title: overscroll-behavior
slug: Web/CSS/overscroll-behavior
tags:
  - CSS
translation_of: Web/CSS/overscroll-behavior
---
{{CSSRef}}

CSS-свойство **`overscroll-behavior`** — это сокращение для свойств {{cssxref("overscroll-behavior-x")}} и {{cssxref("overscroll-behavior-y")}}, которые позволяют управлять поведением прокрутки при достижении границы области прокрутки.

```css
/* Значения-ключевые слова */
overscroll-behavior: auto; /* по умолчанию */
overscroll-behavior: contain;
overscroll-behavior: none;

/* Двойное значение */
overscroll-behavior: auto contain;

/* Глобальные значения */
overflow: inherit;
overflow: initial;
overflow: unset;
```

По умолчанию мобильные браузеры, как правило, обеспечивают эффект «отскока» или даже обновляют страницу при достижении её верхней или нижней части (или другой области прокрутки). Возможно, вы также замечали, что когда поверх страницы с прокруткой расположено диалоговое окно с прокруткой, то при достижении границы прокрутки диалогового окна нижележащая страница начинает прокручиваться. Это называется цепочкой прокрутки (scroll chaining, англ.)

В некоторых случаях такое поведение нежелательно. Вы можете использовать `overscroll-behavior`, чтобы избавиться от нежелательных цепочек прокрутки и поведения страниц браузера по принципу «потяните, чтобы обновить» (pull to refresh, англ.), характерного, например, для приложений Facebook и Twitter.

{{cssinfo}}

## Синтаксис

Свойство `overscroll-behavior` задаётся в виде одного или двух ключевых слов, выбранных из списка значений ниже.

Два ключевых слова определяют значение `overscroll-behavior` по осям `x` и `y` соответственно. Если задано только одно значение, то предполагается, что и `x`, и `y` одинаковы.

### Значения

- `auto`
  - : Поведение по умолчанию.
- `contain`
  - : Поведение для `overscroll-behavior` применяется внутри элемента, для которого установлено это значение (например, эффекты «отскока» или обновления), но не возникают цепочки прокрутки для соседних областей прокрутки, например, нижележащие элементы не будут прокручиваться.
- `none`
  - : Не происходит цепочки прокрутки в соседних областях прокрутки, и по умолчанию предотвращается достижение границы области прокрутки.

### Формальный синтаксис

{{csssyntax}}

## Примеры

В нашем примере [overscroll-поведения](https://mdn.github.io/css-examples/overscroll-behavior/) (см. также код по ссылке [](https://github.com/mdn/css-examples/tree/master/overscroll-behavior)) представлен полностраничный список поддельных контактов и диалоговое окно с чатом.

![](https://mdn.mozillademos.org/files/15778/example.png)

Обе эти области прокручиваются; обычно, если вы прокручиваете окно чата до тех пор, пока не достигнете границы прокрутки, нижележащее окно контактов тоже начнёт прокручиваться, что нежелательно. Предотвратить такое поведение можно, используя `overscroll-behavior-y` (`overscroll-behavior` также подойдет) для окна чата, как показано ниже:

```css
.messages {
  height: 220px;
  overflow: auto;
  overscroll-behavior-y: contain;
}
```

Мы также хотим избавиться от стандартного overscroll-эффекта при прокрутке контактов вверх или вниз (например, Chrome на Android обновляет страницу при прокрутке за пределы верхней границы). Это можно предотвратить, установив для элемента {{htmlelement("body")}} значение `overscroll-behavior: none`:

```css
body {
  margin: 0;
  overscroll-behavior: none;
}
```

## Спецификации

Пока CSSWG не опубликует свой собственный вариант, спецификация может быть найдена только[на Github в репозитории WICG](https://wicg.github.io/overscroll-behavior/).

| Specification                                                                                                            | Status                                       | Comment |
| ------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------- | ------- |
| {{SpecName('Overscroll Behavior', '#propdef-overscroll-behavior', 'overscroll-behavior')}} | {{Spec2('Overscroll Behavior')}} |         |

## Browser compatibility

{{Compat}}

## См. также

- [Take control of your scroll: customizing pull-to-refresh and overflow effects](https://developers.google.com/web/updates/2017/11/overscroll-behavior#demo)
