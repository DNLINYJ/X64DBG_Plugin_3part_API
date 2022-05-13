# DbgAssembleAt

这个函数修改指定地址的汇编指令。
```c++
bool DbgAssembleAt(duint addr, const char *instruction)
```

## 参数

`addr` 需要修改汇编指令的地址

`instruction` 修改的汇编指令

## 返回值

如果修改成功，该函数返回 TRUE，否则返回 FALSE。

## 例子

```c++
if (DbgAssembleAt(0x00401000, "mov eax, ebx")) {
    _plugin_logprintf(u8"修改指令成功")
}
else {
    _plugin_logprintf(u8"修改指令失败")
}
```
