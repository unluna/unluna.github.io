---
title: TS的基本数据类型
date: 2019-09-14 17:07:32
tags: [TS,基础]
categories: TypeScript
cover: /images/TS简介.png
---
# TS的数据类型

## 布尔类型
    const boln: boolean = false;

## 字符串类型
    const str: string = 'string';

## 数字类型
    const num: number = 123;

## 数组类型
    const arr1: number[] = [1, 2, 3];
    const arr2: Array<string> = ['a', 'b', 'c'];
**这里我更喜欢第二种，看起来有科技感**

## 枚举类型
    enum Colors {Red = 5, Green = 10, Yellow = 20};
    const colorName: string = Colors[5]; // "Red"
    const colorIndex: Colors = Colors.Green; // 10
- 枚举么，我对它的理解就是map，每一个成员都有值是最好的，不赋值的话就没什么意义了
- 如果不赋值，其中一个是数字的话，后面的会递增+1
- 如果都不赋值，会得到索引
- 如果其中一个是字符串还不赋值，TS会报错

## 任意数据类型
    let notSure: any = '123';
    notSure = 123;
    const arr3: Array<any> = ['1', 2, true];

## 空数据类型
    function f():void {

    }
- 暂时也就想到这个，表示没有任何返回值的函数
- 声明一个 void 类型的变量没有什么用，因为你只能将它赋值为 undefined 和 null

## null类型
    let n: null = null;

## undefined类型
    let u: undefined = undefined;

<h3 style="color:red">注意！</h3>

**与 void 的区别是，undefined 和 null 是所有类型的子类型。也就是说 undefined 类型的变量，可以赋值给 number 类型的变量：**

    // 这样不会报错
    let num1: number = undefined;

    // 这样也不会报错
    let u: undefined;
    let num2: number = u;

**而 void 类型的变量不能赋值给 number 类型的变量：**

    let u: void;
    let num: number = u;

    // Type 'void' is not assignable to type 'number'.

***
