---
title: "`aria-details`"
description: "Атрибут для элемента с подробной информацией о другом."
authors:
  - tatianafokina
contributors:
  - skorobaeus
keywords:
  - a11y
  - доступность
  - ARIA
  - accessible description
related:
  - a11y/aria-attrs
  - a11y/aria-description
  - a11y/aria-describedby
tags:
  - doka
---

## Кратко

[Свойство связи](/a11y/aria-attrs/#atributy-svyazi) из [WAI-ARIA](/a11y/aria-intro/#specifikaciya). Связывает один элемент с дополнительной подробной информацией о нём. Например, сноску с подробным объяснением термина или ссылку с расшифровкой графика.

`aria-details` не подходит для [доступных описаний](/a11y/accessible-names-and-descs/#dostupnoe-opisanie) — дополнительной информации о цели или содержании элемента.

Содержимое `aria-details` видно на странице и доступно для всех, не только для пользователей [скринридеров](/a11y/screenreaders/).

<aside>

👶 Пока у `aria-details` [частичная поддержка скринридерами](https://a11ysupport.io/tech/aria/aria-details_attribute). Атрибут не поддерживают TalkBack, Narrator и VoiceOver.

</aside>

## Пример

```html
<img
  src="turtle.png"
  alt="Взрослая зелёная черепаха повернулась боком и развернула
  голову вправо. У неё коричневый овальный панцирь со светлыми разводами.
  Лапы похожи на ласты, при этом передние больше задних.
  Снаружи на лапах и на коже головы коричневые пятна, шея и внутрення часть
  лап почти белые."
  aria-details="more-info"
>

<p>
  Узнать больше про
  <a href="https://en.wikipedia.org/wiki/Green_sea_turtle" id="more-info">
    зелёных морских черепах
  </a>.
</p>
```

<iframe title="Картинка с дополнительным описанием" src="demos/image-with-details/" height="440"></iframe>

Скринридеры в этом случае расскажут пользователям, что у картинки есть дополнительное подробное описание.

## Как пишется

Задайте тегу атрибут `aria-details` с любым текстовым значением и свяжите с ним другой элемент через `id`. Атрибут можно использовать для всех тегов и ролей. Важно, чтобы такие элементы и дополнительная информация про них не были скрыты со страницы.

В `aria-details` можно добавлять больше одного значения. Их перечисляют через пробел. Пока несколько значений плохо поддерживаются, так что лучше остановиться на одном.

```html
<img
  src="japanese-spitz.jpg"
  alt="Японский шпиц"
  aria-details="more-details more-link"
>

<details id="more-details">
  <summary>Интересные факты</summary>
  <ul>
    <li>
      Ближайшая родственная порода — немецкий шпиц.
    </li>
    <li>
      Редкая порода, поэтому щенки стоят дорого.
    </li>
    <li>
      Японских шпицов тоже называют «облаками»,
      как самоедов.
    </li>
  </ul>
</details>

<a
  href="https://www.dailypaws.com/dogs-puppies/dog-breeds/japanese-spitz"
  id="more-link"
>
  Статья про японского шпица
</a>
```

`aria-details` обычно содержит много дополнительной информации об элементе, при этом она может находиться на другой странице.

Скринридер прочтёт дополнительную информацию после имени элемента, другой основной информации и его краткого описания.

## Подсказки

💡 `aria-details` похож на устаревший HTML-атрибут `longdesc`.

💡 Если хотите добавить небольшое дополнительное описание к элементу, лучше использовать [`aria-describedby`](/a11y/aria-describedby/).
