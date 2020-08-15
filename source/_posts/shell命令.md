## phonopy 扩胞
`phonopy -d --dim='10 10 10'`
-d displacement 不明白这个参数为什么必要

## python 查看帮助
- pydoc
- intercative help utility
## apt-get update info prompt some error
```
cd /etc/apt/
vi source.list   # if find no error, try grep the info in all files belong to the apt/
```
## system clipboard
`xxx |xsel -b -s -p[default]`
## awk使用举例
 ```
for a in $(ls -d [1-8]*);do echo $a ;cat ${a}/1/cp2k.inp |awk '/ABC/{printf "%s\n%3.1f\n %15.10f%15.10f%15.10f\n%15.10f%15.10f%15.10f\n%15.10f%15.10f%15.10f\n%s\n%d\n%s\n","B20",1.0,$2,0,0,0,$3,0,0,0,$3,"B",20,"Dir"} /&END COORD/{p=0} {if(p==1){print $2,$3,$4}} /SCALED/{p=1}' > POSCAR_${a}; done
```
真长啊，终端里反斜杠换行不熟练

## xargs
`du -h --summarize ./* |grep "^0"|cut -f2| xargs ls`
删除当前目录下大小为0的文件
## 替换castep文件名
`for i in $(ls C.*) ;do mv ${i} O.${i##*.} ;done`
C.开头的文件换成O开头
`for i in $(ls out*);do cp ${i} ../pot/pot_Ti/Ti${i##out} ;done`
## 替换文件内部字符
`sed -i 's/Au/C/g' ARES.CONT_*`
## xarg的奇怪应用
`for i in $(cat parsecPOS );do bohr2angs $i;done |xargs -n 3`
## 并行环境的设置
echo 0 |sudo tee /proc/sys/kernel/yama/ptrace_scope
## 查看静态库的内容
- 查看文件：`ar -t \*.a`
- 查看函数、变量：`nm \*.a`

