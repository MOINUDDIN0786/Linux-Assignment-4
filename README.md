# Linux-Assignment-4
**Ques 1: Create a directory named "MyFiles" in your home directory. Navigate into this directory and list its contents.**

``` 
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

**Ques 7: Use a wildcard character to copy all files from the "Documents" subdirectory of "MyFiles" to another directory named "Backup."**

```
cd /home
```
```
cd MyFiles
```
```
sudo mkdir backup
```
```
cd
```
```
sudo cp /home/MyFiles/Document/* /home/MyFiles/backup/
```

**Output**

![Screenshot from 2024-02-02 10-34-55](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/c332f2ed-32cb-4b7f-bafb-0847d58896df)

**Ques 8 :Execute the ls command to list files in the current directory. Save the output to a file named "file_list.txt." Then, use a pipe to filter the output through grep to display only files with a ".txt" extension.**

```
sudo su
```
```
cd /home/MyFiles/
```
```
touch file_list.txt
```
```
cd Document
```
```
chmod +rwx a.txt b
```
```
cd ..
```
```
chmod +rwx file_list.txt
```
```
cd Document
```
```
ls > ../file_list.txt
```
```
grep '\.txt$' file_list.txt
```

**Output**



![Screenshot from 2024-02-02 11-03-35](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/e3837160-18c3-46b0-a58b-954879d260af)

**Ques 9: Create a new text file named "my_notes.txt" using the touch command. Open the file in the Vim editor, add some text, and save the changes.**
```
cd /home/MyFiles/
```
```
sudo touch my_notes.txt
```
```
sudo vim my_notes.txt
```
**Output**


![Screenshot from 2024-02-02 11-22-48](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/55489b45-3f5d-4b2d-a630-cf437c3fe3d4)

![Screenshot from 2024-02-02 11-26-52](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/ed690270-cf6c-446d-a5a3-9e0bcf7c0b56)

**Ques 10 :Run the date command and store the output in a variable named "current_date." Display the value of the variable and append it to the "my_notes.txt" file.**

```
cd /home/MyFiles/
```
```
sudo su
```
```
current_date=$(date)
```
```
echo "current date : $current_date"
```
```
echo "$current_date" >> my_notes.txt
```
**Output**

![Screenshot from 2024-02-02 11-37-48](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/4bf8b699-36ce-4a7b-be32-6654a0858846)

![Screenshot from 2024-02-02 11-42-47](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/c46260f6-236f-4214-b0a5-88cf3fa08e7b)


**Ques 11 : Edit the Bash startup script (e.g., .bashrc) to set an environment variable named "CUSTOM_PATH" to a specific directory path. Ensure the variable is available in new shell sessions.**
```
vim .bashrc
```
```
export CUSTOM_PATH="/home/MyFiles/Document"
```
```
source ~/.bashrc
```
```
echo $CUSTOM_PATH
```
**Output**

![Screenshot from 2024-02-02 14-08-23](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/4e3eb4d2-84aa-4618-9db8-baf1270593f4)

![Screenshot from 2024-02-02 14-09-58](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/35038695-cd2b-4e5e-b76a-7309a1663c88)

**Ques 12 : Use the echo command to add a new line of text to the "my_notes.txt" file without overwriting existing content. Verify that the new text is appended.**

```
cd /home/MyFiles
```
```
sudo su
```
```
echo "I am writing text in new line" >> my_notes.txt
```
```
cat my_notes.txt
```
**Output**

![Screenshot from 2024-02-02 14-21-47](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/66aef82f-825f-4bd8-bb3a-bb924d3f9aaa)

**Ques 13 : List all files in the "/etc" directory, filter the output to include only those containing the word "conf," and save the result to a file named "conf_files.txt."**

```
ls /etc | grep 'conf' > conf_files.txt
```
```
vim conf_files.txt
```
**Ques 14 : Open the "my_notes.txt" file in Vim. Use Vim's search and replace functionality to replace all occurrences of the word "important" with "critical." Save the changes.**

```
cd /home/MyFiles
```
```
sudo vim my_notes.txt
```
**After opening file write below  command after press shift + colon
```
%s/important/critical/g
```
**Output**




























