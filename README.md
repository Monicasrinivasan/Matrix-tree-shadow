# Matrix-tree-shadow
#include<stdio.h>
#include<stdlib.h>
int main()
{
    int r,c,i,j,a[100][100],count=0;
    char ch;
    scanf("%d %d",&r,&c);       //read row and column.
    for(i=0;i<r;i++)
    {
        for(j=0;j<c;j++)
        {
            scanf("%d\t",&a[i][j]);
        }
    }
    scanf("\n%c",&ch);         //read the character.
    switch(ch)
    {
        case 'L':              //check the number of trees if the shadow falls left.
        for(i=0;i<r;i++)
        {
            for(j=0;j<c;j++)
            {
                if(a[i][j]==1 && a[i][j+1]==0 && j+1<=c-1)
                {
                    count++;
                }
            }
        }
        break;
        case 'R':            //check the number of trees if the shadow falls right.
        for(i=0;i<r;i++)
        {
            for(j=0;j<c;j++)
            {
                if(a[i][j]==1 && a[i][j-1]==0 && j>0 )
                {
                    count++;
                }
            }
        }
        break;
        case 'F':        //check the number of trees if the shadows falls front(up to down)
        for(i=0;i<r;i++)
        {
            for(j=0;j<c;j++)
            {
                if(a[i][j]==1 && a[i-1][j]==0 && i>0)
                {
                    count++;
                }
            }
        }
        break;
        case 'B':       //check the number of trees if the shadow falls back(down to up)
        for(i=0;i<r;i++)
        {
            for(j=0;j<c;j++)
            {
                if(a[i][j]==1 && a[i+1][j]==0 && i+1<=r-1)
                {
                    count++;
                }
            }
        }
        break;
    }
    printf("%d",count);
}
