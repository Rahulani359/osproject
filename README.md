# osproject
#include <stdio.h>
int main()
{

    	int n, m,i,j,k;
	printf("enter number of process");
	scanf("%d",&n);
	printf("enter number of resources");
	scanf("%d",&m);
	int alloc[n];
	int max[n];
	int avail=m;
	int maxneed=0;
	for(i=0;i<n;i++)
	{
	printf("enter number of resources allocated to process %d ",i);
	scanf("%d",&alloc[i]);
	printf("enter maximum resources need for process %d ",i);
	scanf("%d",&max[i]);
	}
    int f[n], ans[n], ind = 0;
    for (k = 0; k < n; k++) {
        f[k] = 0;
    }
    int need[n];
    for (i = 0; i < n; i++) {
    	if(max[i]>m)
		{
		printf("\nSafe sequence is not possible");
		exit(0);
		}
}
    for (i = 0; i < n; i++) {
         need[i] = max[i] - alloc[i];
    	printf("\nneed of process %d is %d ",i,need[i]);
	}
int al=0;
for(i=0;i<n;i++)
{
al+=alloc[i];
}
for(i=0;i<n;i++)
{
maxneed+=need[i];
}
avail-=al;
	printf("\navailable resources after allocation is %d",avail);
	if(maxneed>(n+m))
	{
		printf("\nSafe sequence is not possible");
	}
	else
	{
while(ind<n)
{
if(need[i]<avail && f[i]==0)
{
ans[ind]=i;
f[i]=1;
avail+=alloc[i];
printf("\n%d process finished available resources is %d",i,avail);
ind++;
}
i++;
if(i>n)
i=0;
}
 printf("\nFollowing is the SAFE Sequence\n");
    for (i = 0; i < ind-1; i++)
        printf(" P%d ->", ans[i]);
	printf(" P%d\n",ans[ind-1]);
    return (0);
}}

