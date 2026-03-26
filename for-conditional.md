# for conditional 

### structure
for **variable_name** in **List**
do 
    **acction**
done


### Lab Task 

We have some images under the directory `/home/bob/images`. Develop a script `/home/bob/rename-images.sh` to rename all files within the images folder 
that has extension ´jpeg´ to `jpg.` A file with any other extension should remain the same.

- Tip: Use a `for` loop to iterate over the files within /home/bob/images

- Tip: Use an `if` conditional to check if the file extension is jpeg.

- Tip: Use `mv` to rename a file.

### Solution 

Directory `Images` has all the images `files` inside it,  thats why we use **ls** insted of **cat**  
- `ls` is used to list all file inside of a directory
- `cat` is used to list what is inside of a file
```
for file in $(ls images)
do 
```
if condition
```
if [[ $file = *.jpeg ]]
then
```
1. `$()` Command substitution: Shell executes wherevee is inside the parentheses
2. `echo $file`: Prints what is in the $file variable eg. cat.jpeg
3. `pipe` **|** Takes the output of **echo** and sends it directly input **sed** command
4. `sed` Stream editor: replace .jpeg extension to .jpg

```
new_name=$(echo $file | sed ´s/.jpeg/.jpg/g´
```
We need don´t need to specify the full path  `/home/bob/image` cause when we create $file variable, linux saves the directory name as part of the variable. 
```
     mv /image/$new_name /image/$new_name
  fi
done  
```

