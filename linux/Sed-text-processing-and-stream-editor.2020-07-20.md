# Sed text processing and stream editor 
 ## Basic
**Replace**
```sh
sed -i 's/before/after/' file
```
**Execute multiple commands in the same line**
```sh
sed -i -e '' -e '' file
```
**Value**
```sh
sed -i 's/'$value'/after/' file 
```
**Save**
```sh
sed -i 's/abc\(def\)/ghi/' file # ghidef
sed -i 's/abc\(def\)/\1/' file # defdef
sed -i 's/abc.*/[&]/' file # [abc.*] 
```
**Delete**
```sh
sed -i '1,$d' file # remove 1-end line
sed -i 's/abc//' file # delete all abc
```
## Note
- Special matching characters need to be escaped

## Question
- Cannot execute when the variable contains special characters

## Refrence
- [Linux命令大全-文件和目录管理-sed](https://man.linuxde.net/sed)
- [linux在线手册-sed](http://linux.51yip.com/search/sed)
- [Linux sed 命令](https://www.runoob.com/linux/linux-comm-sed.html)