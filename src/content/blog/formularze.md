---
title: "Jak zakodować przyjazny użytkownikom formularz?"
description: "5 snippetów CSS, które poprawią UX Twoich formularzy"
pubDate: "06/02/2024"
tags:
  - HTML
  - CSS
  - Snippety
---

Weźmy na warsztat prosty formularz kontaktowy.

```html
<form>
  <!-- Imię -->
  <label for="name">Name</label>
  <input id="name" type="text" />

  <!-- E-mail (pole wymagane) -->
  <label for="email">Email</label>
  <input id="email" type="email" required />

  <!-- Treść wiadomości (pole wymagane) -->
  <label for="message">Message</label>
  <textarea id="message" required></textarea>

  <button type="submit">Send</button>
</form>
```

## Responsywne pole tekstowe
Jeżeli chcemy, żeby nasze pole tekstowe dopasowywało się do ilości treści wpisywanej przez użytkownika, możemy sięgnąć po 🔥 hot nowość – właściwość [field-sizing](https://developer.mozilla.org/en-US/docs/Web/CSS/field-sizing). 

 `field-sizing: content` sprawi, że nasza `textarea` dopasuje się do długości tekstu, dlatego wyjściowo (przy pustym polu) będzie miała zawsze jedną linię. Aby wizualnie odróżnić ją od zwykłego inputu i pokazać, że jest w niej miejsce na rozpisanie się, możemy nadać jej minimalną wysokość.

```css
textarea {
  field-sizing: content;
  min-height: 3lh;
  max-height: 8lh;
}
```
`field-sizing: content` nie jest jeszcze wspierana przez wszystkie przeglądarki (np. Safari, Firefox). Jednak w duchu *progressive enhancement* możemy już dziś użyć jej w kodzie produkcyjnym.
