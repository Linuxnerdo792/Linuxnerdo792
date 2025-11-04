Absolutely! I’ll make **60 tricky and challenging questions** for `grep`, `sed`, and `awk` in **Markdown format**, including multiple-choice style where applicable. I’ll also include an **answer key** at the end. I’ll organize them in **three sections**: `grep`, `sed`, and `awk`.

Here’s the complete set:

---

# **Linux Text Processing Questions**

## **Section 1: grep (Search)**

1. Which `grep` option allows searching recursively through directories?
   a) `-r`
   b) `-i`
   c) `-v`
   d) `-c`

2. How to search for the word "error" in a file ignoring case?
   a) `grep "error" file.txt`
   b) `grep -i "error" file.txt`
   c) `grep -v "error" file.txt`
   d) `grep -r "error" file.txt`

3. Which command prints the line numbers along with matching lines?
   a) `grep -n pattern file`
   b) `grep -l pattern file`
   c) `grep -c pattern file`
   d) `grep -i pattern file`

4. How to search for lines **not containing** "success"?
   a) `grep -v "success" file`
   b) `grep -i "success" file`
   c) `grep -n "success" file`
   d) `grep -r "success" file`

5. `grep "^a"` matches:
   a) Lines starting with "a"
   b) Lines ending with "a"
   c) Lines containing "a" anywhere
   d) Lines with only "a"

6. `grep "a$"` matches:
   a) Lines ending with "a"
   b) Lines starting with "a"
   c) Lines containing "a" anywhere
   d) Lines without "a"

7. To count number of matches of "fail" in file:
   a) `grep -n fail file`
   b) `grep -c fail file`
   c) `grep -v fail file`
   d) `grep -l fail file`

8. Match lines with **exact word** "cat" only:
   a) `grep "cat" file`
   b) `grep -w "cat" file`
   c) `grep -x "cat" file`
   d) `grep -i "cat" file`

9. Print 2 lines **before and after** match of "error":
   a) `grep -A 2 -B 2 "error" file`
   b) `grep -C 2 "error" file`
   c) `grep -n "error" file`
   d) Both a & b

10. Search for either "fail" or "error":
    a) `grep "fail|error" file`
    b) `grep -E "fail|error" file`
    c) `grep -e "fail" -e "error" file`
    d) b & c

11. How to search **hidden files** recursively?
    a) `grep -r "pattern" .*`
    b) `grep "pattern" *`
    c) `grep -i "pattern" file`
    d) `grep -n "pattern" file`

12. Match lines containing digits only:
    a) `grep "[0-9]" file`
    b) `grep "^[0-9]*$" file`
    c) `grep "\d" file`
    d) a & b

13. Search pattern "abc" **but exclude lines with xyz**:
    a) `grep -v "xyz" file | grep "abc"`
    b) `grep "abc" file | grep -v "xyz"`
    c) `grep "abc" file -v "xyz"`
    d) b

14. Which prints file names containing the pattern?
    a) `grep -l "pattern" *`
    b) `grep -n "pattern" *`
    c) `grep -c "pattern" *`
    d) `grep -v "pattern" *`

15. Match lines with **tab character**:
    a) `grep "\t" file`
    b) `grep "\\t" file`
    c) `grep -P "\t" file`
    d) c

16. Search "apple" ignoring case, display **count only**:
    a) `grep -ci "apple" file`
    b) `grep -i "apple" file`
    c) `grep -c "apple" file`
    d) `grep -v "apple" file`

17. Match lines **starting with number followed by colon**:
    a) `grep "^[0-9]:" file`
    b) `grep "^[0-9]+:" file`
    c) `grep "^[0-9]{1,}:" file`
    d) a & b

18. Print lines **without empty lines**:
    a) `grep "." file`
    b) `grep -v "^$" file`
    c) `grep -c "." file`
    d) a & b

19. Use grep to search a **multi-line pattern**:
    a) `grep -Pzo "pattern"`
    b) `grep -r "pattern"`
    c) `grep -i "pattern"`
    d) `grep -v "pattern"`

20. `grep -o "pattern"` prints:
    a) Only matching part
    b) Full line
    c) Line number
    d) File name

---

## **Section 2: sed (Search & Replace)**

21. Replace **first occurrence** of "apple" with "orange":
    a) `sed 's/apple/orange/' file`
    b) `sed 's/apple/orange/g' file`
    c) `sed 's/apple/orange/1' file`
    d) a

22. Replace **all occurrences** of "apple" with "orange":
    a) `sed 's/apple/orange/g' file`
    b) `sed 's/apple/orange/' file`
    c) `sed 's/apple/orange/1' file`
    d) b

23. Delete **empty lines** from file:
    a) `sed '/^$/d' file`
    b) `sed 's/^$//g' file`
    c) `sed '/./d' file`
    d) a

24. Print lines **2 to 5** using sed:
    a) `sed -n '2,5p' file`
    b) `sed '2,5p' file`
    c) `sed '2,5d' file`
    d) a

25. Replace **line containing pattern**:
    a) `sed '/pattern/c\New line' file`
    b) `sed 's/pattern/New line/' file`
    c) `sed '/pattern/d' file`
    d) a

26. Insert a line **before** match:
    a) `sed '/pattern/i\Insert line' file`
    b) `sed '/pattern/a\Insert line' file`
    c) `sed 's/pattern/Insert line/' file`
    d) a

27. Append a line **after** match:
    a) `sed '/pattern/i\Insert line' file`
    b) `sed '/pattern/a\Insert line' file`
    c) `sed 's/pattern/Insert line/' file`
    d) b

28. Replace **word with special char** like `/`:
    a) `sed 's/\/home\/user/\/mnt\/disk/g' file`
    b) `sed 's#/home/user#/mnt/disk#g' file`
    c) `sed 's|/home/user|/mnt/disk|g' file`
    d) b & c

29. Delete **first line** of file:
    a) `sed '1d' file`
    b) `sed 'd1' file`
    c) `sed '1,1d' file`
    d) a & c

30. Delete **last line** of file:
    a) `sed '$d' file`
    b) `sed 'd$' file`
    c) `sed '1d' file`
    d) a

31. Replace **only 2nd occurrence** in line:
    a) `sed 's/pattern/new/2' file`
    b) `sed 's/pattern/new/1' file`
    c) `sed 's/pattern/new/g' file`
    d) a

32. Replace **case-insensitive**:
    a) `sed 's/pattern/new/I' file`
    b) `sed 's/pattern/new/i' file`
    c) `sed 's/pattern/new/g' file`
    d) b

33. Print **lines not matching** pattern:
    a) `sed -n '/pattern/!p' file`
    b) `sed '/pattern/!p' file`
    c) `sed '/pattern/p' file`
    d) a

34. Replace pattern using **backreference**:
    a) `sed 's/\(foo\)\(bar\)/\2\1/' file`
    b) `sed 's/(foo)(bar)/\2\1/' file`
    c) `sed 's/foo/bar/' file`
    d) a

35. Delete **lines containing digits**:
    a) `sed '/[0-9]/d' file`
    b) `sed '/[0-9]/p' file`
    c) `sed 's/[0-9]//g' file`
    d) a

36. Replace **first word of each line**:
    a) `sed 's/^[^ ]*/NewWord/' file`
    b) `sed 's/^.*$/NewWord/' file`
    c) `sed 's/ /NewWord/' file`
    d) a

37. Transform **commas to colons**:
    a) `sed 's/,/:/g' file`
    b) `sed 's/:/,/g' file`
    c) `sed 's/,/:/' file`
    d) a

38. Replace **tab character** with space:
    a) `sed 's/\t/ /g' file`
    b) `sed 's/\\t/ /g' file`
    c) `sed 's/\s/ /g' file`
    d) a

39. Change **2nd line** only:
    a) `sed '2s/.*/New text/' file`
    b) `sed 's/.*/New text/2' file`
    c) `sed '2d' file`
    d) a

40. Replace **word only if line contains another pattern**:
    a) `sed '/pattern1/s/pattern2/new/g' file`
    b) `sed 's/pattern2/new/g /pattern1' file`
    c) `sed '/pattern2/s/pattern1/new/g' file`
    d) a

---

## **Section 3: awk (Manipulate Formatted Data)**

41. Print **first column** of a file:
    a) `awk '{print $1}' file`
    b) `awk '{print $0}' file`
    c) `awk '{print $2}' file`
    d) a

42. Print **sum of 2nd column**:
    a) `awk '{sum+=$2} END{print sum}' file`
    b) `awk '{sum+=$1} END{print sum}' file`
    c) `awk '{print $2}' file`
    d) a

43. Print lines **where 3rd column > 50**:
    a) `awk '$3>50' file`
    b) `awk '$3>=50' file`
    c) `awk '$2>50' file`
    d) a

44. Print **line number and first column**:
    a) `awk '{print NR, $1}' file`
    b) `awk '{print $1, NR}' file`
    c) `awk '{print $0}' file`
    d) a

45. Print **only lines where 1st column is "Alice"**:
    a) `awk '$1=="Alice"' file`
    b) `awk '$1="Alice"' file`
    c) `awk '/Alice/' file`
    d) a

46. Print **total number of lines**:
    a) `awk 'END{print NR}' file`
    b) `awk '{print NR}' file`
    c) `awk 'END{print $0}' file`
    d) a

47. Print **average of column 2**:
    a) `awk '{sum+=$2} END{print sum/NR}' file`
    b) `awk '{sum+=$2} END{print sum}' file`
    c) `awk '{print $2}' file`
    d) a

48. Print lines **where 1st column starts with A**:
    a) `awk '$1~/^A/' file`
    b) `awk '$1=="A"' file`
    c) `awk '/^A/' file`
    d) a

49. Print **last column** of file:
    a) `awk '{print $NF}' file`
    b) `awk '{print $1}' file`
    c) `awk '{print $0}' file`
    d) a

50. Swap **1st and 2nd columns**:
    a) `awk '{print $2, $1}' file`
    b) `awk '{print $1, $2}' file`
    c) `awk '{print $0}' file`
    d) a

51. Print **lines containing "error" in any column**:
    a) `awk '/error/' file`
    b) `awk '$0~/error/' file`
    c) `awk '{if($0 ~ /error/) print $0}' file`
    d) All

52. Print **columns 1 and 3 only**:
    a) `awk '{print $1, $3}' file`
    b) `awk '{print $1 $3}' file`
    c) `awk '{print $0}' file`
    d) a

53. Sum **columns 2 and 3** and print result:
    a) `awk '{print $2+$3}' file`
    b) `awk '{sum=$2+$3; print sum}' file`
    c) `awk '{print $0}' file`
    d) a & b

54. Print **lines where 2nd column is empty**:
    a) `awk '$2==""' file`
    b) `awk '$2~/^$/' file`
    c) `awk '{if($2=="") print $0}' file`
    d) All

55. Print **lines with more than 3 columns**:
    a) `awk 'NF>3' file`
    b) `awk 'NF>=3' file`
    c) `awk 'NF<3' file`
    d) a

56. Count **lines with "pass" in column 4**:
    a) `awk '$4=="pass"{count++} END{print count}' file`
    b) `awk '$4=="pass"{print NR}' file`
    c) `awk '$4=="pass"' file | wc -l`
    d) a & c

57. Print **unique values of 1st column**:
    a) `awk '!seen[$1]++{print $1}' file`
    b) `awk '{print $1}' file | sort | uniq`
    c) `awk '{print $1}' file`
    d) a & b

58. Print **2nd column only if 1st column is Alice**:
    a) `awk '$1=="Alice"{print $2}' file`
    b) `awk '{if($1=="Alice") print $2}' file`
    c) Both

59. Replace **column 2 with "Unknown" if empty**:
    a) `awk '{$2=($2=="")?"Unknown":$2; print}' file`
    b) `awk '{if($2=="") $2="Unknown"; print}' file`
    c) Both

60. Print **columns in reverse order**:
    a) `awk '{for(i=NF;i>=1;i--) printf $i " "; print ""}' file`
    b) `awk '{print $NF, $1}' file`
    c) a

---

## **Answer Key**

**grep:** 1-a, 2-b, 3-a, 4-a, 5-a, 6-a, 7-b, 8-b, 9-d, 10-d, 11-a, 12-d, 13-b, 14-a, 15-c, 16-a, 17-a, 18-d, 19-a, 20-a
**sed:** 21-a, 22-a, 23-a, 24-a, 25-a, 26-a, 27-b, 28-d, 29-d, 30-a, 31-a, 32-b, 33-a, 34-a, 35-a, 36-a, 37-a, 38-a, 39-a, 40-a
**awk:** 41-a, 42-a, 43-a, 44-a, 45-a, 46-a, 47-a, 48-a, 49-a, 50-a, 51-d, 52-a, 53-d, 54-d, 55-a, 56-d, 57-d, 58-c, 59-c, 60-a

---

If you want, I can
