# Linking  
## ELF format  
| ELF header| |
| --- | --- |
| .text | code |
| .rodata | read only data, like printf format string and jump tables |  
| .data | 初始化的全局变量和static变量 |  
| .bss | 未初始化的全局变量和static变量 and 初始化为0的全局变量和static变量 |   
| .symtab | 在这个程序中定义和引用的 函数 和 全局变量 |
| .rel.text |
| .rel.data |
| .debug |
| .line |
| .strtab |  
| COMMON | 未初始化的全局变量 |  
| section header table |   

