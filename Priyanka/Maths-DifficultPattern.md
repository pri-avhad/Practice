# Title: Maths-Print a pattern 

Question link: https://www.hackerrank.com/challenges/printing-pattern-2/problem

### Code:

```
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

![image](https://user-images.githubusercontent.com/64562764/120239302-961a3d00-c27b-11eb-8363-7e841171f1b1.png)

### Comments:

This was interesting because the element to be printed had a new constraint. It was as the distance from the center
