# 最小と最大横幅（min-max.html）

## min-width

```html
<div class="min-width">
  <p class="nomin">最小幅なし</p>
  <p class="min">最小幅100px</p>
</div>
```
```css
.min-width {
  width: 200px;/*親要素大きめ*/
  background:skyblue
}
.min-width .nomin {/*最小幅なし*/
  background:gray;
  width: 50%
}
.min-width .min {/*最小幅あり*/
  background:orange;
  width: 50%;
  min-width: 100px
}
```

## max-width

```html
<div class="max-width">
  <p class="nomin">最大幅なし</p>
  <p class="min">最大幅100px</p>
</div>
```
```css
.max-width {
  width: 100px;/*親要素小さめ*/
  background:skyblue
}
.max-width .nomin {/*最大幅なし*/
  background:gray;
  width: 80%
}
.max-width .min {/*最大幅あり*/
  background:orange;
  width: 80%;
  max-width: 100px
}
```