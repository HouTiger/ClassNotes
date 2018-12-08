# Vitual Memory  
> 2018.12.05  

| | | 
| --- | --- | 
| 0x0000 7FFF FFFF FFFF | 所以64位机器的内存大小为 2 ^ 48|  
| stack | | 
| | | 
| shared library | |
| |  
| heap | | 
| data | | 
| text | | 
| 0x400000 | |  
| | |  48
| 0x000000 | |    

## Solve the address conflicts  —— mapping: add a level of indirection
* 没有什么是一次间接寻址解决不了的  
* implementation: translate address transparently (by the System/Hardware etc.)   
* CPU->MMU(memory management unit)->(translation)->Physical Address  
* Physical Memory > VM in 32bits age  usually  
    VM > PM in 64bits usually  

## VM as a tool for caching  
* cache  
    * `i$` (icache)  
        | valid | tag | data |
    * `d$` (dcache)  
        | valid | tag | data | dirty |
* data transport  
    reg <- 64bit <- cache <- 32byte/64byte <- memory <- 512byte <- hardware  

* vitual memory  
    `pm` is cache for `vm`    
    vitual memory block are **stored/or not/or cannot be accessed** by process in the physical memory  
    vitual memory is a **file** stored in hardware    
    so the strategy must be write back, each time write to hardware almost require 1 ms  
* page table  

    || valid | disk address | P (权限)|   
    | --- | --- | --- | --- |  
    |PTE 0| 0 | NULL | |  
    |PTE 1| 1 | M_ptr1 | Read/Write/Exec/SUP |  
    |PTE 2| 1 | M_ptr2 | |  
    |PTE 3| 0 | D_ptr3 | |  

    ptr is the physical address of page in **PM** or physical address on **disk** 

    here comes **page hit** and **page fault**  
    it's call **demand paging**  

## VM as a tool for memory management  
* sharing data by VM
* Linking  
    each prigram have same virtual address 
* Loading    
    * **execve** create PTEs marked as invalid    
        allocates vitual pages for `.text` and `.data`  
        copy them in on demand   
## VM as a tool for Memory Protection  

|| valid | disk address | P (权限)|   
| --- | --- | --- | --- |  
|PTE 0| 0 | NULL | |  
|PTE 1| 1 | ptr1(literally PPN) | Read/Write/Exec/SUP |  
|PTE 2| 1 | ptr2 | |  
权限限制了process 的操作

## address mapping  
* parameters  
    VPO | late 12bits  | virtual page offset |  
    VPN | front | virtual page number |  
    PPO | same as VPO, offset in   
    PPN | physical pointer | physical page number |     
* CR3 (control register)   
    * (page table base register) | PTBR  
        only one, for the ongoing process  
    * Page Table is stored in a PM page  
    * process changing only need changes PTBR  
* CPU -> (Virtual Address) -> MMU -> (PTE Address) -> Memory -> (hit) -> (PTE) -> MMU -> 
* but this way, we turn a **one time** memory access into **two times**  
    so we use TLB, stored in L1 cache, much faster, usually one time memory access    
    vitual address is saparated into  
    | TLB tag | TLB index | VPO | 
    | --- | --- | --- | --- |   
    TLB is like      
    | v | tag | PTE |   
    | --- | --- | --- |
* but 64bits TLB is 512GB, too large!  
    multi-level TLB  
    two-level page table  
    one level 1 PTE points two 2^22 byte in memory  
    so it's 4KB, which explains why program address starts from 4K  


