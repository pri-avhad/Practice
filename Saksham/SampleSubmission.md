# Title: Maths- Print a pattern 
(will be the same as the file name: Maths-Pattern.md)

Question link: https://www.hackerrank.com/challenges/printing-pattern-2/problem

### Code:

```
//Copy paste your code here
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

int main() 
{

    int n;
    scanf("%d", &n);
  	for (int i = 1; i < 2*n ; i++){
        for (int j = 1; j < 2*n ; j++){
            printf(1 + max(Math.abs(n-i), Math.abs(n-j)));
        }
        printf("\n");
    }
    return 0;
}
```

### Output:

Attach a screenshot of your output by dragging the image here

![image](https://user-images.githubusercontent.com/64562764/120107657-86b5c980-c17f-11eb-9c74-8a19aa7358ea.png)
