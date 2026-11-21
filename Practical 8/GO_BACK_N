Go-Back-N_ARQ.c


#include <stdio.h>

int main()
{
    int n, window, i, j;

    printf("Enter number of frames: ");
    scanf("%d", &n);

    printf("Enter window size: ");
    scanf("%d", &window);

    int ack[n];

    for(i = 0; i < n; i++)
        ack[i] = 0;

    i = 0;

    while(i < n)
    {
        printf("\nSending frames: ");

        for(j = i; j < i + window && j < n; j++)
        {
            if(ack[j] == 0)
                printf("%d ", j + 1);
        }

        printf("\nEnter last acknowledged frame number: ");
        scanf("%d", &j);

        if(j >= i + 1 && j <= n)
        {
            for(int k = i; k < j; k++)
                ack[k] = 1;

            i = j;
            printf("Acknowledgement received. Window slides.\n");
        }
        else
        {
            printf("Invalid acknowledgement. Retransmitting frames from %d.\n", i + 1);
        }
    }

    printf("\nAll frames transmitted successfully!\n");

    return 0;
}
