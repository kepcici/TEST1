---
id: 5900f3891000cf542c50fe9c
title: 'Завдання 29: різні степені'
challengeType: 1
forumTopicId: 301941
dashedName: problem-29-distinct-powers
---

# --description--

Розглянемо усі цілочисельні комбінації $a^b$ за умови 2 ≤ a ≤ 5 та 2 ≤ b ≤ 5:

<div style='padding-left: 4em;'>
  2<sup>2</sup>=4, 2<sup>3</sup>=8, 2<sup>4</sup>=16, 2<sup>5</sup>=32 <br>
  3<sup>2</sup>=9, 3<sup>3</sup>=27, 3<sup>4</sup>=81, 3<sup>5</sup>=243 <br>
  4<sup>2</sup>=16, 4<sup>3</sup>=64, 4<sup>4</sup>=256, 4<sup>5</sup>=1024 <br>
  5<sup>2</sup>=25, 5<sup>3</sup>=125, 5<sup>4</sup>=625, 5<sup>5</sup>=3125 <br>
</div>

Якщо їх розташувати в порядку зростання, вилучивши повторення, ми отримаємо таку послідовність з 15 різних членів:

<div style='padding-left: 4em;'>
  4, 8, 9, 16, 25, 27, 32, 64, 81, 125, 243, 256, 625, 1024, 3125
</div>

Скільки різних членів має послідовність, згенерована $a^b$ за умови 2 ≤ `a` ≤ `n` та 2 ≤ `b` ≤ `n`?

# --hints--

`distinctPowers(15)` має повернути число.

```js
assert(typeof distinctPowers(15) === 'number');
```

`distinctPowers(15)` має повернути 177.

```js
assert.strictEqual(distinctPowers(15), 177);
```

`distinctPowers(20)` має повернути 324.

```js
assert.strictEqual(distinctPowers(20), 324);
```

`distinctPowers(25)` має повернути 519.

```js
assert.strictEqual(distinctPowers(25), 519);
```

`distinctPowers(30)` має повернути 755.

```js
assert.strictEqual(distinctPowers(30), 755);
```

# --seed--

## --seed-contents--

```js
function distinctPowers(n) {

  return n;
}

distinctPowers(30);
```

# --solutions--

```js
const distinctPowers = (n) => {
  let list = [];
  for (let a=2; a<=n; a++) {
    for (let b=2; b<=n; b++) {
      let term = Math.pow(a, b);
      if (list.indexOf(term)===-1) list.push(term);
    }
  }
  return list.length;
};
```
