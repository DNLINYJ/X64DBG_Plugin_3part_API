# DbgModBaseFromName

这个函数获取指定模块名的基址。
```c++
duint DbgModBaseFromName(const char *name)
```

## 参数

`name` 模块名

## 返回值

如果获取成功，该函数返回基址，否则返回 FALSE。

## 例子

```c++
duint base_address = DbgModBaseFromName("ntdll.dll");
if (base_address){
    _plugin_logprintf(u8"ntdll.dll 的基址为 0x%p", base_address)
}
```
