# Fizz Buzz
写一个程序，输出从 1 到 n 数字的字符串表示。

1. 如果 n 是3的倍数，输出“Fizz”；

2. 如果 n 是5的倍数，输出“Buzz”；

3. 如果 n 同时是3和5的倍数，输出 “FizzBuzz”。

## 思路
可以说是非常简单的一道循环题目了。看了一圈，发现几个有意思的解法。
- 同时是3和5的倍数可以用对15取余来做
- 最后转字符串的花样比较多：
    - `""+i`
    - `i.toString`
    - 像我一样用字符串模板：\`${i}\`     
## 代码
    /**
     * @param {number} n
     * @return {string[]}
     */
    var fizzBuzz = function (n) {
        let result = [];
        for (let i = 1; i <= n; i++) {
            if (i % 5 == 0 && i % 3 == 0) {
                result.push("FizzBuzz");
            } else if (i % 5 == 0) {
                result.push("Buzz");
            } else if (i % 3 == 0) {
                result.push("Fizz");
            } else {
                result.push(`${i}`);
            }
        }
        return result;
    };
有点意思的代码：  

        /**
         * @param {number} n
         * @return {string[]}
         */
        var fizzBuzz = function (n) {
            let res = []
            for (let i = 1; i <= n; i++) {
                let temp = String(i)
                if (i % 3 === 0) {
                    temp = 'Fizz'
                }
                if (i % 5 === 0) {
                    temp = isNaN(temp) ? 'FizzBuzz' : 'Buzz'
                }
                res.push(temp)
            }
            return res
        };