# npm으로 sass설치 시 Sass version incompatible 오류
- https://codingapple.com/forums/topic/sass%EC%84%A4%EC%B9%98-%EC%8B%9C-%EC%98%A4%EB%A5%98/

# Error: Node Sass version 6.0.1 is incompatible with ^4.0.0.
## solution
- node_modules/sass-loader/lib/loader.js 로 이동
```js
...

 } else if (implementation === "node-sass") {
        if (!semver.satisfies(version, "^6.0.0")) {  // 요기 수정: ^4.0.0 -> ^6.0.0 으로 변경
            throw new Error("Node Sass version " + version + " is incompatible with ^4.0.0.");
        }
...
```