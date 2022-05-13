# DbgDisasmFastAt

这个函数获取指定地址的反汇编信息。
```c++
void DbgDisasmFastAt(duint addr, BASIC_INSTRUCTION_INFO *basicinfo)
```

## 参数

`addr` 需要快速反汇编的地址

`basicinfo` BASIC_INSTRUCTION_INFO结构体

## 返回值

无。

## 例子

```c++
/* BASIC_INSTRUCTION_INFO 结构体定义
typedef struct
{
    DWORD type; // 地址种类 value|memory|addr
    VALUE_INFO value; //immediat
    MEMORY_INFO memory;
    duint addr; // 地址
    bool branch; // 这个指令是不是 jumps/calls 指令
    bool call; // 这个指令是不是 call 指令
    int size; // 指令大小
    char instruction[MAX_MNEMONIC_SIZE * 4]; // 汇编指令
} BASIC_INSTRUCTION_INFO; 
*/

// 获取指定地址的汇编指令
BASIC_INSTRUCTION_INFO basicinfo;
DbgDisasmFastAt(0x00401000, &basicinfo);

std::string temp_string = basicinfo.instruction;

_plugin_logprintf(u8"获取地址 0x%p 汇编指令为 %s", 0x00401000, temp_string.c_str())
```
