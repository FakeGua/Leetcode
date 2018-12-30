# 326. Power of Three
给定一个整数，写一个函数来判断它是否是 3 的幂次方。

示例 1:

    输入: 27
    输出: true
示例 2:

    输入: 0
    输出: false
示例 3:

    输入: 9
    输出: true
示例 4:

    输入: 45
    输出: false
进阶：
你能不使用循环或者递归来完成本题吗？
## 思路
两种思路：

    1.  设定一个初始值，只要这个初始值不大于输入值就乘3。  
        如果初始值与输入值相等，则返回true。  
        否则返回false。

    2.  属于投机取巧的方法：由于输入是int，正数范围是0-231。
        在此范围中允许的最大的3的次方数为319=1162261467。
        那么我们只要看这个数能否被n整除即可。
## 代码
    /**
    * @param {number} n
    * @return {boolean}
    */
    var isPowerOfThree = function(n) {
        let i = 1;
        while(i <= n ){
            if(i == n){
                return true;
            }
            i *= 3;
        }
        return false;
    };
---
    /**
    * @param {number} n
    * @return {boolean}
    */
    var isPowerOfThree = function(n) {
        return n > 0 && 1162261467%n == 0;
    };
