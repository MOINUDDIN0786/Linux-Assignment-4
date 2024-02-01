# Linux-Assignment-4
**Ques 1: Create a directory named "MyFiles" in your home directory. Navigate into this directory and list its contents.**

``` bash
cd /home
```
```
sudo mkdir MyFiles
```
```
cd MyFiles
```
```
 ls
```

**Output**

![image](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/23131560-ddb6-4b12-8876-8258c4e073fa)

**Ques 2: Copy a file named "document.txt" from your home directory to the "MyFiles" directory. Move the file to a subdirectory named "Documents" within "MyFiles."**

``` 
cd /home
```
```
sudo touch document.txt
```
```
sudo cp document.txt MyFiles/
```
```
cd MyFiles/
```
```
sudo mkdir -p Document
```
```
sudo mv MyFiles/document.txt MyFiles/Document
```








