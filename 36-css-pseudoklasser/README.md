# Test av pseudoklasser

På [denne nettsiden](pseudoklasse-sitatblokk.html) tester jeg pseudoklassen `::after` i en sitatblokk (`blockqote`).

Jeg har gitt sitatblokken en selvvalg attributt i HTML-koden: `name`. `name` er navnet på personen som har opphavet til sitatet.

For å automatisk legge til navnet på opphavspersonen etter sitatet (og få fine anførseltegn rundt sitatet) så brukte jeg følgende CSS-kode.

```css
blockquote::before {
  content: "«";
}
blockquote::after {
  content: "» \a — "attr(name);
  white-space: pre;
  font-style: italic;
}
```

`blockquote::before` gjelder rett før `blockquote` elementet, og vi ber CSS om å sette inn et anførselstegn for å starte sitatet.

I `blockquote::after` så gjør vi noen flere interessante saker.

- `\a` er kode for å legge til et linjeskift i tekst
- `attr(name)` gir beskjed om at vi skal sette inn verdien fra attributten `name` som vi har definert i HTML-koden. Legg merke til at dette står utenfor hermetegnene.
- `white-space: pre;` gjør at nettleseren kommer til å ta hensyn til `\a`. Uten å definere denne så vil `\a` bare vises teksten `\a` i nettleseren.
- Vi setter også teksten til å være kursiv
