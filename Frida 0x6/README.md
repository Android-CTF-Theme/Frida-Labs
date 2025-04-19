## Lab 06 综合学习

直接运行 Lab3 的 hook 脚本会报错

```bash
Error: Cannot access an instance field without an instance
```

个人感觉是把 3 和 4 和 5 结合了起来

```javascript
Java.performNow(function() {
  Java.choose('com.ad2001.frida0x6.MainActivity', {
    onMatch: function(instance) {
      console.log("Instance found");

      var checker = Java.use("com.ad2001.frida0x6.Checker");
      var checker_obj  = checker.$new();  // Class Object
      checker_obj.num1.value = 1234;
      checker_obj.num2.value = 4321;

      instance.get_flag(checker_obj)
    },
    onComplete: function() {}
  });
});
```

![](images/06flag.png)
