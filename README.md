# spoiler-span

```html
<span class="spoiler-text">
```
```css
.spoiler-text {
    position: relative;
    display: inline-block;
    cursor: pointer;
    color: transparent;
    transition: color 0.1s;
}
.spoiler-text::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: black;
    opacity: 1;
    transition: opacity 0.1s;
    border-radius: 2px;
    z-index: 1;
}
.spoiler-text.revealed {
    color: inherit;
}
.spoiler-text.revealed::before {
    opacity: 0.07;
}
```
```js
document.addEventListener("DOMContentLoaded", function() {
    const spoilers = document.querySelectorAll('.spoiler-text');
    spoilers.forEach(spoiler => {
        spoiler.addEventListener('click', function() {
            this.classList.toggle('revealed');
        });
    });
});
```
