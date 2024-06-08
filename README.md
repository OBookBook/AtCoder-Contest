# サントリープログラミングコンテスト 2024（AtCoder Beginner Contest 357）

## 使用言語

- TypeScript

## 結果

![aavsavav](https://github.com/OBookBook/AtCoder-Contest/assets/130152109/ec1ed47d-52bf-4911-9757-d70f6ebdbc6c)

## 問題 A - Sanitize Hands

- [問題ページ](https://atcoder.jp/contests/abc357/tasks/abc357_a)
- [提出ページ](https://atcoder.jp/contests/abc357/submissions/54359618)

### 提出コード

```ts
// @see https://atcoder.jp/contests/abc357/tasks/abc357_a
// 入力例
// 5 10
// 2 3 2 5 3

function Main(input: string): void {
  const lines: string[] = input.split("\n"); // [ '5 10', '2 3 2 5 3' ]
  let [N, M]: number[] = lines[0].split(" ").map(Number); // N = 5 , M = 10
  const H: number[] = lines[1].split(" ").map(Number); // H = [ 2, 3, 2, 5, 3 ]

  let count: number = 0;
  H.forEach((hand) => {
    if (M >= 0) M -= hand;
    if (M >= 0) count++;
  });
  console.log(count); // 3
}

Main(require("fs").readFileSync("/dev/stdin", "utf8").trim());
```

## 問題 B - Uppercase and Lowercase

- [問題ページ](https://atcoder.jp/contests/abc357/tasks/abc357_b)
- [提出ページ](https://atcoder.jp/contests/abc357/submissions/54370294)

### 提出コード

```ts
// @see https://atcoder.jp/contests/abc357/tasks/abc357_b
// 入力例: AtCoder
function Main(input: string): void {
  const lines: string[] = input.split("\n"); // [ 'AtCoder' ]
  const S: string = lines[0]; // 'AtCoder'
  // @see https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/String/match
  const upperCount: number = (S.match(/[A-Z]/g) || []).length; // 2 [ 'A', 'C' ]
  const lowerCount: number = (S.match(/[a-z]/g) || []).length; // 5 [ 't', 'o', 'd', 'e', 'r' ]

  if (upperCount >= lowerCount) {
    console.log(S.toUpperCase());
  } else {
    console.log(S.toLowerCase()); // atcoder
  }
}

Main(require("fs").readFileSync("/dev/stdin", "utf8").trim());
```
