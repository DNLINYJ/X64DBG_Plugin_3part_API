# DbgGetModuleAt

这个函数获取指定地址所在的模块名。
```c++
bool DbgGetModuleAt(duint addr, char *text)
```

## 参数

`addr` 地址

`text` 存放模块名的变量

## 返回值

如果获取成功，该函数返回 TRUE，否则返回 FALSE。

## 例子

```c++
char* module_name = new char[256];
bool ret = DbgGetModuleAt(uiAddr, module_name);
string module_name_str = module_name;

if (module_name_str != "ntdll") {
    _plugin_logprintf("该地址不在 ntdll.dll 模块中!");
}

delete[] module_name;
```
