
#include <stdio.h>
#include<stdlib.h>
#define ll long long int
#define rep(i,n) for(ll i=1;i<=n;i++)
#define loop(i,a,b) for(ll i=a;i<=b;i++)


//entering array
int inArr(int a[],int n)
{
    for(int i=1;i<=n;i++)
    {
        scanf("%d",&a[i]);
    }
}
// Sum of array
int sumArr(int a[],int n)
{
    int sum=0;
    for(int i=1;i<=n;i++)
    {
        sum+=a[i];
    }
    return sum;
}
//printing array
int outArr(int a[],int n)
{
   for(int i=1;i<=n;i++)
   {
       printf("%d",a[i]);
   }
}

//Sorting of array
int sortArr(int a[],int n)
{
    int temp;
    for(int i=1;i<=n;i++)
    {
        for(int j=1;j<=i;j++)
        {
            if(a[i]<a[j])
		    {
    			temp=a[j];
			    a[j]=a[i];
                a[i]=temp;	
            }
        }
    }
	outArr(a,n);
}

int main(void) 
{
    int T,i;
    scanf("%d",&T);
    for(i=0;i<T;i++)
    {
        ll n;
        ll p=1,flag=1,temp=0;
        scanf("%lld",&n);
        ll a[n];
        for(ll j=1;j<=n;j++)
       
        {
            scanf("%lld",&a[j]);
            if(j>1 && p==1)
            {
                if(a[j-1]>a[j])
                {
                    temp=a[j];
                    a[j]=a[j-1];
                    a[j-1]=temp;
                    p=0;
                }
            }
        }
             for(int j=2;j<=n;j++)
            {
                if(a[j-1]>a[j])
                {
                    flag=0;
                  //  break;
                }
            
            }
            if(flag==0)
            printf("no\n");
            else
            printf("yes\n");
            
       
    }
    
	return 0;
}

