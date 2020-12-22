# C++基础

## 1.简单说一下C++的继承，封装和多态

* 封装：将一个模块的内部数据或操作隐藏起来，其他程序只能通过该模块提供的公开操作来访问他们的保护措施称为信息隐藏。而将这一组数据与这些数据上的相关操作组织在一起的措施称为封装。
* 继承：在一个或若干个已知类的基础上，经过适当的修改，扩充构成一个新类，该类具有原来作为基础的类的特征。
* 多态：在程序中同一符号或名字在不同的情况下具有不同解释的现象称为多态性。编译时多态：通过重载机制获得，包括函数重载和运算符重载；运行时多态：通过继承结合虚函数的动态绑定获得。

## 2.虚函数和虚表

* 虚函数：在一个类中用保留字Virtual定义的成员函数。
* 虚表：虚函数表里是函数指针，指向虚函数的指针。就是C++编译器实现运行时多态的封装。

## 3.什么时候和为什么要用虚析构

首先什么是虚析构，虚析构就是析构函数为虚函数。
那么为什么要用虚析构呢，是为了delete基类指针指向派生类时防止子类得数据不会被释放造成内存泄露。

## 4.纯虚函数

在基类中声明但又没有定义的虚函数。

## 5.函数重载(overload)和函数重写(override)

* 函数重载：在声明函数原型时形参的个数不同或者相同个数的参数但对应位置的参数类型不同，两个或多个函数可以共用同一个名字。
* 函数重写：即重定义，意思是在派生类中定义一个函数原型与继承成员一模一样的成员函数。

## 6.引用与指针的区别

* 初始化要求不同。引用在创建的同时必须初始化，即引用到一个有效的对象；而指针在定义的时候不要求初始化，可以在定义后面的任何地方重新赋值。
* 可修改性不同。引用一旦被初始化为指向一个对象，他就不能被改变为另一个对象的引用；而指针在任何时候都可以改变为指向另一个对象。
* 不存在NULL的引用，它必须总是指向某个对象；指针可以是NULL，不需要总是指向某些对象。

## 7.深拷贝与浅拷贝

* 深拷贝与浅拷贝最本质的区别在于是否真正获取到一个对象的复制实体，而不是引用。
* 浅拷贝只是复制指向某个对象的指针，而不是复制对象本身，新旧对象还是共享同一块内存。
* 深拷贝会创造一个一模一样的对象，新对象与原对象不共享内存，修改新对象不会改变原对象的值。

## 8.new和delete(new[] 和 delete [])

## 9.智能指针以及智能指针的实现

* 智能指针的基本思想就是以栈对象管理资源，离开作用域自动销毁时调用析构函数来释放资源。
* unique_ptr: 它对对象持有独有权，两个unique_ptr不能指向同一个对象，不共享其管理的对象，无法复制到其他unique_ptr，无法通过值传递到函数，也无法用于需要副本的任何STL算法，只能移动unique_ptr，对资源管理权实现转移，原始的unique_ptr不再拥有此资源。
* shared_ptr:允许多个指针指向同一个对象，其利用引用计数的方式实现了对所管理的对象所有权的分享，允许多个shared_ptr共同管理同一个对象。
* weak_ptr:可以从一个shared_ptr或者另一个weak_ptr对象构造而来，最大的作用在于协助shared_ptr工作，可获得资源得观测权，只是对shared_ptr 的引用，不改变其引用计数，当被观察的shared_ptr 失效后，相应的weak_ptr也会失败。

## 10.const的使用

## 11.static的使用

## 12.string的实现

# STL基础







