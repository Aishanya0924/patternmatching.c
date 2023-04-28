# patternmatching.c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// Driver code
int main()
{
        FILE* ptr;
        char ch;
        int count=0;
        int ai=0;
        ptr = fopen("ai.txt", "r");

        if (NULL == ptr) {
                printf("file can't be opened \n");
        }

        printf("\n");

        while (!feof(ptr)) {
                ch = fgetc(ptr);
                if (count>=50){
                        printf("%c",'\n');
                }
                else{

                        printf("[%d %c]\n",count,ch);
                        if (ch=='A'){
                                ch = fgetc(ptr);
                                count++;
                                printf("[%d %c]\n",count,ch);
                                if (ch=='I'){
                                        printf ("FOUND AI\n");
                                        ai++;
                                }
                        }
                }
        count++;
        }
        printf("Number of characters= %d\n",count-1);
        printf("AI was printed %d times",ai);
        printf("\n");
        fclose(ptr);
        return 0;
}
![image](https://user-images.githubusercontent.com/132048421/235085049-a19c7fd7-fd45-478f-8206-757a38d44b6e.png)
