# css-interview-questions (2025–2026)


<img width="385" height="196" alt="image" src="https://github.com/user-attachments/assets/efde9464-c333-4152-af34-d96d593de9da" />

```jsx
<div class="container">
  <div class="row">
    <div class="box">A</div>
    <div class="box">B</div>
  </div>
  <div class="box c">C</div>
</div>

```

```jsx
.container {
  width: 400px;
  border: 2px solid black;
}

.row {
  display: flex;
}

.box {
  flex: 1;
  height: 100px;
  border: 1px solid black;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: bold;
}

.c {
  height: 100px;
}

```

<img width="392" height="208" alt="image" src="https://github.com/user-attachments/assets/158c2853-da9f-469c-9222-0a19f16196d1" />

```jsx
<div class="container">
  <div class="row">
    <div class="box">A</div>
    <div class="box">B</div>
  </div>
  <div class="row">
    <div class="box">C</div>
    <div class="box">D</div>
  </div>
</div>

```

```jsx
.container {
  width: 400px;
  border: 2px solid black;
}

.row {
  display: flex;
}

.box {
  flex: 1;
  height: 100px;
  border: 1px solid black;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: bold;
}

```

<img width="575" height="196" alt="image" src="https://github.com/user-attachments/assets/74848c26-7025-442e-bda8-fee5dea530b7" />

```jsx
<div class="container">
  <div class="row top">
    <div class="box">A</div>
    <div class="box">B</div>
    <div class="box">C</div>
  </div>

  <div class="row bottom">
    <div class="box d">D</div>
    <div class="box e">E</div>
  </div>
</div>

```

```jsx
.container {
  width: 600px;
  border: 2px solid black;
}

.row {
  display: flex;
}

.box {
  height: 100px;
  border: 1px solid black;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: bold;
}

/* Top row: 3 equal boxes */
.top .box {
  flex: 1;
}

/* Bottom row: D bigger than E */
.d {
  flex: 2;
}

.e {
  flex: 1;
}

```

## **Media Query**

```jsx
<div class="container">
  <div class="box">A</div>
  <div class="box">B</div>
  <div class="box">C</div>
</div>

```

```jsx
.container {
  display: flex;
}

.box {
  flex: 1;
  padding: 20px;
  border: 1px solid black;
}

/* Mobile view */
@media (max-width: 600px) {
  .container {
    flex-direction: column;
  }
}

```

***Result***
- Desktop → A B C in a row
- Mobile → A B C stacked

## **Why order matters**

***For screen ≤ 480px***
- max-width: 768px matches
- max-width: 480px also matches

👉 The last rule should be the smallest screen, so it overrides correctly.

```jsx
/* Desktop */
.box {
  width: 300px;
}

/* Tablet */
@media (max-width: 768px) {}

/* Mobile */
@media (max-width: 480px) {}

```
❌ ***Wrong order (common mistake)***
```jsx
@media (max-width: 480px) { ... }
@media (max-width: 768px) { ... }

```

### Grid 

***HTML***
```jsx
<div class="grid-container">
  <div class="box">1</div>
  <div class="box">2</div>
  <div class="box">3</div>
  <div class="box">4</div>
  <div class="box">5</div>
  <div class="box">6</div>
</div>
```
***CSS***
```jsx
.grid-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
}

.box {
  background: lightblue;
  padding: 20px;
  text-align: center;
}
```

`Explanation`

- display: grid → enables grid layout
- grid-template-columns: repeat(3,1fr) → 3 equal columns
- gap → space between grid items
