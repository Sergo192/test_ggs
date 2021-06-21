## Basic work with files

- Create directory test1

```console
sergiy@TheDivision:~/Desktop/test$ mkdir test1
```

- Create file test1.txt inside the test1 directory.

sergiy@TheDivision:~/Desktop/test$ cd test1/
sergiy@TheDivision:~/Desktop/test/test1$ touch test1.txt

-   Create copy of folder test1 with name test2.
  
sergiy@TheDivision:~/Desktop/test/test1$ cd ../
sergiy@TheDivision:~/Desktop/test$ cp -R test1/ test2

-    Delete file test1.txt inside test2 directory.

sergiy@TheDivision:~/Desktop/test$ cd test2/
sergiy@TheDivision:~/Desktop/test/test2$ rm test1.txt

-    Rename test2 folder into directory_without_file

sergiy@TheDivision:~/Desktop/test$ mv test2 directory_without_file
sergiy@TheDivision:~/Desktop/test$ ls

-    Insert 'test1' text into test1/test1.txt file.

sergiy@TheDivision:~/Desktop/test$ cd test1/
sergiy@TheDivision:~/Desktop/test/test1$ echo test1 > test1.txt 

-    print the text from the test1/test1.txt file.

sergiy@TheDivision:~/Desktop/test/test1$ cat test1.txt 

-    Insert 'test2' into the end of test1/test1.txt file.

sergiy@TheDivision:~/Desktop/test/test1$ echo test2 >> test1.txt 

-    print the text from the test1/test1.txt file.

sergiy@TheDivision:~/Desktop/test/test1$ cat test1.txt 
test1
test2

- check the size of test1 directory

sergiy@TheDivision:~/Desktop/test$ du -sh test1/
8.0K	test1/


## Permissions

-   Create test directory and block access for all to it.

sergiy@TheDivision:~/Desktop/permissions$ mkdir test
sergiy@TheDivision:~/Desktop/permissions$ chmod a-rwx test/ 
sergiy@TheDivision:~/Desktop/permissions$ ls -l
total 4
d--------- 2 sergiy sergiy 4096 Jun 21 18:30 test


-   Try to remove that directory.

sergiy@TheDivision:~/Desktop/permissions$ rm -rf test/

-    Create simple script which prints current date. Try to execute it.

sergiy@TheDivision:~/Desktop/permissions$ echo date +"%m/%d/%y" > script.sh
sergiy@TheDivision:~/Desktop/permissions$ sh script.sh 
06/21/21

## Log checking

-  Count lines in the file test.txt.

sergiy@TheDivision:~/Desktop/gitrep/test_ggs$ wc -l test.txt 
200 test.txt

- Show last 3 lines from the test.txt file. 

sergiy@TheDivision:~/Desktop/gitrep/test_ggs$ tail -n3 test.txt 
75.127.11.5 - - [02/Apr/2021:04:11:03 -0500] "GET /index.php/using-joomla/extensions/components/users-component/login-form HTTP/1.1" 301 707 "http://riuconstructora.com.do/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.36 Edge/B08C390C"
114.119.145.5 - - [02/Apr/2021:04:11:21 -0500] "GET /tanix-shop/14479wfzr4606990.htm HTTP/1.1" 404 708 "-" "Mozilla/5.0 (Linux; Android 7.0;) AppleWebKit/537.36 (KHTML, like Gecko) Mobile Safari/537.36 (compatible; PetalBot;+https://aspiegel.com/petalbot)"
114.119.137.70 - - [02/Apr/2021:04:12:55 -0500] "GET /tokka-com/19577wfzr4989999040074.htm HTTP/1.1" 404 708 "-" "Mozilla/5.0 (Linux; Android 7.0;) AppleWebKit/537.36 (KHTML, like Gecko) Mobile Safari/537.36 (compatible; PetalBot;+https://aspiegel.com/petalbot)"


-  Hom many uniq IP addresses accessed the website ? 


-  IP address with most requests.


-  Top 3 IP addresses by amount of POST requests.


-  Which IP addresses received 403 error ? 


- Task with * . Write script to show which pages Google checked from the website 

## Replace

Replace IP address with most requests on 127.0.0.1 in test.txt file 
