# Linking  
## what do linkers do?
* Symble Resolution
    * in this step, the linker associates one refference with only one definiton  
* Relocation
    * Relocates symbols from their relative locations in `.o` files to final absolute memory locations in the executable 
## three kinds of object files
* relocatable files
* executable files
* shared object file


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



## Linker's Symble Rules
* strong symbol
    * fuctions and initialized globals
* weak symbol
    * uninitialized globals
    * or extern
* multiple strong 
    * error
* one strong and more weak
    * point to the strong one
* multiple weak
    * pick an arbitrary one  

* common是伪节，.bss的虚拟长度和在内存中的实际长度是不一定一样的，有可能文件中没多长，但内存中很长  
