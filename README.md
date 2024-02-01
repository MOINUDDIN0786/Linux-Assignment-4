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

**output**

![image](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/bf0f22c5-c182-4d44-aef1-fe8d341d6a0c)


**Ques 3 : Create an empty file named "notes.txt" in the "MyFiles" directory. Afterward, delete the file.**

``` 
cd /home/MyFiles/
```
```
sudo touch notes.txt
```
```
sudo rm -rf notes.txt
```



**Output**

![Screenshot from 2024-02-01 17-11-06](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/f9ebf3d0-df42-49d7-b305-0e38dc627fe5)


**Ques 4 : Create a hard link named "hardlink.txt" for the file "document.txt" within the "Documents" subdirectory. Also, create a symbolic link named "symlink.txt" in the same location.**

```
cd /home/MyFiles/Document
```
```
ln document.txt hardlink.txt
```
```
ln -s document.txt symlink.txt
```
**Output**

![Screenshot from 2024-02-01 17-21-21](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/424d0692-131b-4ecb-8977-a00907417bde)

**Ques 5 : In the "MyFiles" directory, use a single command to list all files that start with the letter "a" and have a ".txt" extension.**

```
sudo ls /home/MyFiles/a*.txt
```

**Output**

![Screenshot from 2024-02-01 17-32-14](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/f8b35588-3c63-4a52-a457-08176d04d991)


**Ques 6: Rename all files in the "Documents" subdirectory of "MyFiles" with a ".bak" extension. Ensure the original file names are preserved.**

```
cd /home/MyFiles
```
```
sudo vim rename.sh
```
```
#!/bin/bash

rename_extension=".bak"

for file in *; do
    if [ -f "$file" ]; then
        rename_file="$file$rename_extension"
        cp "$file" "$rename_file"
        echo "Renamed File $file as $rename_file"
    fi
done
```
```
cd Document
```
```
touch a.txt b c.txt d.txt
```
```
sudo bash ../rename.sh
```
**Output**

![Screenshot from 2024-02-01 18-21-48](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/53789776-4d53-41ae-aa22-9fc2689807b0)















