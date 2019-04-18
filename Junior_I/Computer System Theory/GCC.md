* gcc
    * `gcc -E a.c > preprocess.txt` get `.i`
    * `gcc -S a.c` get `.s`  
    * `gcc -c a.c` get `.o`  


    * `gcc -o prog a.c` get `executable program called prog`  
* objdump
    * `objdump -d prog/a.o` get disassembled file  

`cat`
`touch`
`mkdir`
* `ls`
    * `-a` all of them, including `.` `..`
    * `-l` detail
    * `-F` mark dir and executable