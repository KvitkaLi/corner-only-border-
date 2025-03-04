# corner-only-border-
Corner-Only Border Around An Image
Цей CSS код використовує декілька цікавих властивостей для стилізації зображення (img). 
Давайте розберемо його частинами:
HTML
<img src="https://picsum.photos/id/1068/250/250">

CSS
img {
  --s: 80px; /* corner size */
  padding: 15px; /* the gap */
  border: 8px solid #69D2E7;
  mask:
    conic-gradient(at var(--s) var(--s),#0000 75%,#000 0)
     0 0/calc(100% - var(--s)) calc(100% - var(--s)),
    conic-gradient(#000 0 0) content-box;
}

--s: 80px;
Це користувацька змінна CSS, яка задає розмір кута (розмір, який буде використаний для маски). 
Змінна --s встановлена на 80px.
padding: 15px;
Властивість padding додає внутрішні відступи навколо зображення. Тут відступ складає 15px з усіх боків.

border: 8px solid #69D2E7;
Це звичайна рамка, яка має товщину 8px і колір #69D2E7 (світло-блакитний відтінок).

mask:
Властивість mask дозволяє застосувати маску до елементу, щоб приховати частини зображення. Тут використовуються два градієнти, які формують складну маску.
Перший градієнт (conic-gradient(at var(--s) var(--s),#0000 75%,#000 0) 0 0/calc(100% - var(--s)) calc(100% - var(--s))):
Це конічний градієнт, що починається з точки var(--s) var(--s) (тобто з точки 80px, 80px від верхнього лівого кута елементу).

Градієнт переходить від прозорого кольору (#0000) до чорного (#000), і цей перехід триває на 75% від діаметра, після чого зображення буде повністю чорним.

calc(100% - var(--s)) задає розміри маски, щоб вона не перекривала край зображення, а закривала лише центральну частину.
Другий градієнт (conic-gradient(#000 0 0) content-box;):
Це ще один конічний градієнт, який просто застосовує чорний колір до центральної частини зображення.
content-box означає, що цей градієнт буде застосовуватись лише до внутрішнього контенту (включаючи лише відступи, але не рамки).

Як це працює:
В результаті, цей код створює маску, яка розділяє зображення на кілька частин. На зображенні буде видно центральну частину, а навколо неї буде розміщена кольорова рамка з ефектом градієнта.
Задаючи mask, ми регулюємо, які частини зображення будуть видимими, а які — прихованими.
Цей код може використовуватись для створення різноманітних ефектів зображень, наприклад, для спеціальних форм або для створення цікавих рамок із заокругленими кутами.
