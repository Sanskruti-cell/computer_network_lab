Distance_Vector_Routing_Algo.c


#include <stdio.h>

#define INF 999

int main()
{
    int n, i, j, k;
    int cost[10][10], dist[10][10];
    int nextHop[10][10];
    int updated;

    printf("Enter number of routers: ");
    scanf("%d", &n);

    printf("Enter cost matrix (999 for no connection):\n");

    for(i = 0; i < n; i++)
    {
        for(j = 0; j < n; j++)
        {
            scanf("%d", &cost[i][j]);

            dist[i][j] = cost[i][j];

            if(i == j)
                nextHop[i][j] = i;
            else if(cost[i][j] != INF)
                nextHop[i][j] = j;
            else
                nextHop[i][j] = -1;
        }
    }

    // Distance Vector Routing
    do
    {
        updated = 0;

        for(i = 0; i < n; i++)
        {
            for(j = 0; j < n; j++)
            {
                for(k = 0; k < n; k++)
                {
                    if(cost[i][k] != INF &&
                       dist[k][j] != INF &&
                       cost[i][k] + dist[k][j] < dist[i][j])
                    {
                        dist[i][j] = cost[i][k] + dist[k][j];
                        nextHop[i][j] = k;
                        updated = 1;
                    }
                }
            }
        }

    } while(updated);

    // Display routing tables
    for(i = 0; i < n; i++)
    {
        printf("\nRouting Table for Router %d\n", i + 1);
        printf("Destination\tCost\tNext Hop\n");

        for(j = 0; j < n; j++)
        {
            printf("%d\t\t", j + 1);

            if(dist[i][j] == INF)
                printf("INF\t");
            else
                printf("%d\t", dist[i][j]);

            if(nextHop[i][j] == -1)
                printf("-\n");
            else
                printf("%d\n", nextHop[i][j] + 1);
        }
    }

    return 0;
}
