原

``` javascript
function getUserDescribe(name) {
    let str; // 存储判断结果
    if (name.length > 3) {
        str = "名字太长";
    } else if (name.length < 2) {
        str = "名字太短";
    } else if (name[0] === "陈") {
        str = "小陈";
    } else if (name[0] === "李" && name !== "李鹏") {
        str = "小李";
    } else if (name === "李鹏") {
        str = "管理员";
    } else {
        str = "此人比较神秘！";
    }
    // 对判断结果str的一些处理
    // ......
    console.log(str);
    return str;
}
```

优化后
``` javascript
const describeForNameMap = [
    [(name) => name.length > 3, () => "名字太长"],
    [(name) => name.length < 2, () => "名字太短"],
    [(name) => name[0] === "陈", () => "小陈"],
    [(name) => name === "大鹏", () => "管理员"],
    [(name) => name[0] === "李" && name !== "李鹏", () => "小李"],
];

function getUserDescribe(name) {
    let str; // 存储判断结果
    const getDescribe = describeForNameMap.find((item) => item[0](name));
    if (getDescribe) {
        str = getDescribe[1]();
    } else {
        str = "此人比较神秘！";
    }
    // 对判断结果str的一些处理
    // ......
    console.log(str);
    return str;
}
```
