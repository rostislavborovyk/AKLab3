# AKLab3

## Program code

```c
#include <stdlib.h>
#include <stdio.h>
#include <getopt.h>


int main(int argc, char *argv[]) {

    int help = 0;
    int key_a = 0;
    int key_b = 0;

    const char *short_options = "hab";

    const struct option long_options[] = {
            {"help", no_argument, NULL, 'h'},
            {"key_a", optional_argument, NULL, 'a'},
            {"key_b", optional_argument, NULL, 'b'},
            {NULL, 0, NULL, 0},
    };
    int rez = 0;

    while ((rez = getopt_long(argc, argv, short_options, long_options, NULL)) != -1) {
        switch (rez) {
            case 'h':
                if (!help){
                    printf("Arg: Help\n");
                    help = 1;
                }
                break;
            case 'a':
                if (!key_a){
                    printf("Arg: a\n");
                    key_a = 1;
                }
                break;
            case 'b':
                if (!key_b){
                    printf("Arg: b\n");
                    key_b = 1;
                }
                break;

        };
    };
    printf("\n");
};
```

## Testing program

![Test](img/test1.png)
