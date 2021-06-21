## Basic work with files

- Create directory test1

```console
sergiy@TheDivision:~/Desktop/test$ mkdir test1
```

- Create file test1.txt inside the test1 directory.

```console
sergiy@TheDivision:~/Desktop/test$ cd test1/
sergiy@TheDivision:~/Desktop/test/test1$ touch test1.txt
```

-   Create copy of folder test1 with name test2.

```console  
sergiy@TheDivision:~/Desktop/test/test1$ cd ../
sergiy@TheDivision:~/Desktop/test$ cp -R test1/ test2
```
-    Delete file test1.txt inside test2 directory.

```console
sergiy@TheDivision:~/Desktop/test$ cd test2/
sergiy@TheDivision:~/Desktop/test/test2$ rm test1.txt
```
-    Rename test2 folder into directory_without_file

```console
sergiy@TheDivision:~/Desktop/test$ mv test2 directory_without_file
sergiy@TheDivision:~/Desktop/test$ ls
```
-    Insert 'test1' text into test1/test1.txt file.

```console
sergiy@TheDivision:~/Desktop/test$ cd test1/
sergiy@TheDivision:~/Desktop/test/test1$ echo test1 > test1.txt 
```
-    print the text from the test1/test1.txt file.

```console
sergiy@TheDivision:~/Desktop/test/test1$ cat test1.txt 
```
-    Insert 'test2' into the end of test1/test1.txt file.

```console
sergiy@TheDivision:~/Desktop/test/test1$ echo test2 >> test1.txt 
```
-    print the text from the test1/test1.txt file.

```console
sergiy@TheDivision:~/Desktop/test/test1$ cat test1.txt 
test1
test2
```
- check the size of test1 directory

```console
sergiy@TheDivision:~/Desktop/test$ du -sh test1/
8.0K	test1/
```

## Permissions

-   Create test directory and block access for all to it.

```console
sergiy@TheDivision:~/Desktop/permissions$ mkdir test
sergiy@TheDivision:~/Desktop/permissions$ chmod a-rwx test/ 
sergiy@TheDivision:~/Desktop/permissions$ ls -l
total 4
d--------- 2 sergiy sergiy 4096 Jun 21 18:30 test
```

-   Try to remove that directory.

```console
sergiy@TheDivision:~/Desktop/permissions$ rm -rf test/
```
-    Create simple script which prints current date. Try to execute it.

```console
sergiy@TheDivision:~/Desktop/permissions$ echo date +"%m/%d/%y" > script.sh
sergiy@TheDivision:~/Desktop/permissions$ sh script.sh 
06/21/21
```
## Log checking

-  Count lines in the file test.txt.

```console
sergiy@TheDivision:~/Desktop/gitrep/test_ggs$ wc -l test.txt 
200 test.txt
```
- Show last 3 lines from the test.txt file. 

```console
sergiy@TheDivision:~/Desktop/gitrep/test_ggs$ tail -n3 test.txt 
75.127.11.5 - - [02/Apr/2021:04:11:03 -0500] "GET /index.php/using-joomla/extensions/components/users-component/login-form HTTP/1.1" 301 707 "http://riuconstructora.com.do/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.36 Edge/B08C390C"
114.119.145.5 - - [02/Apr/2021:04:11:21 -0500] "GET /tanix-shop/14479wfzr4606990.htm HTTP/1.1" 404 708 "-" "Mozilla/5.0 (Linux; Android 7.0;) AppleWebKit/537.36 (KHTML, like Gecko) Mobile Safari/537.36 (compatible; PetalBot;+https://aspiegel.com/petalbot)"
114.119.137.70 - - [02/Apr/2021:04:12:55 -0500] "GET /tokka-com/19577wfzr4989999040074.htm HTTP/1.1" 404 708 "-" "Mozilla/5.0 (Linux; Android 7.0;) AppleWebKit/537.36 (KHTML, like Gecko) Mobile Safari/537.36 (compatible; PetalBot;+https://aspiegel.com/petalbot)"
```

-  Hom many uniq IP addresses accessed the website ? 

```console
sergiy@TheDivision:~/Desktop/gitrep/test_ggs$ awk '{print $1}' test.txt | sort -u > unique.txt
sergiy@TheDivision:~/Desktop/gitrep/test_ggs$ wc -l unique.txt 
64 unique.txt
```

-  IP address with most requests.

```console
sergiy@TheDivision:~/Desktop/gitrep/test_ggs$ awk '{freq[$1]++} END{for (i in freq) print i, "(" freq[i] ")"}' test.txt
66.249.73.149 (1)
209.58.157.26 (1)
114.119.154.237 (14)
114.119.131.71 (1)
186.179.34.150 (1)
95.160.35.99 (1)
5.157.33.107 (1)
185.191.171.14 (1)
114.119.135.229 (10)
114.119.152.12 (8)
64.38.250.180 (1)
5.62.34.15 (1)
114.119.155.23 (9)
51.158.123.35 (1)
36.78.44.103 (1)
102.128.141.46 (1)
114.119.141.77 (15)
13.66.139.92 (3)
114.119.137.70 (13)
75.127.11.5 (1)
95.163.255.165 (1)
207.46.13.36 (1)
158.222.14.178 (1)
104.223.32.179 (1)
123.13.60.225 (1)
157.55.39.112 (1)
95.163.255.169 (1)
114.119.159.79 (11)
216.244.66.242 (2)
95.163.255.185 (1)
175.137.148.124 (1)
175.157.112.24 (1)
196.242.20.138 (1)
196.247.224.37 (1)
66.249.65.93 (10)
66.249.65.94 (10)
66.249.65.95 (6)
117.218.127.242 (1)
40.77.167.86 (2)
185.191.171.22 (1)
213.226.101.18 (1)
172.107.174.194 (1)
185.191.171.25 (1)
82.211.50.137 (1)
185.191.171.40 (1)
185.191.171.41 (1)
182.227.203.85 (1)
185.191.171.43 (1)
168.90.199.106 (1)
196.18.156.230 (1)
125.99.34.94 (1)
89.36.224.244 (1)
95.163.255.171 (1)
186.179.36.82 (1)
114.119.140.234 (16)
114.119.130.151 (12)
123.13.122.71 (2)
185.191.171.5 (1)
95.163.255.195 (3)
93.10.69.29 (1)
131.153.31.219 (1)
5.164.196.10 (1)
114.119.145.5 (8)
66.249.73.147 (1)
```


-  Top 3 IP addresses by amount of POST requests.


-  Which IP addresses received 403 error ? 


- Task with * . Write script to show which pages Google checked from the website 

## Replace

Replace IP address with most requests on 127.0.0.1 in test.txt file 
