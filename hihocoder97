#include <iostream>
#include <stdio.h>
#include <string.h>
#include <string>
#include <queue>
#include <stack>
#include <vector>
#include <math.h>
#include <map>
#include <stdlib.h>
#include <algorithm>

#define eps 1e-5
#define inf 0x3f3f3f3f
#define Linf 0x3f3f3f3f3f3f3f3f
#define max(a,b) ((a)>(b)?(a):(b))
#define min(a,b)  ((a)<(b)?(a):(b))
#define lson l,m,rt<<1
#define rson m+1,r,rt<<1 | 1
#define lc rt<<1
#define rc rt<<1 | 1
#define getx2(a)  ((a)*(a))
#define Pi acos(-1.0)

typedef long long LL;
using namespace std;
#define MM 76543
#define N 1010

LL ex_gcd(LL a,LL b,LL &x,LL &y)
{
    if(!b)
    {
        x=1;
        y=0;
        return a;
    }
    LL g=ex_gcd(b,a%b,x,y);
    LL t=x;
    x=y;
    y=t-a/b*y;
    return g;
}
LL m[N],r[N];
LL getLineEqualAns(int n)
{
    LL M=m[0],R=r[0];
    for(int i=1; i<n; i++)
    {
        LL x=-1,y=-1;
        LL d=ex_gcd(M,m[i],x,y);
        LL c=r[i]-R;
        if(c%d)return -1;
        LL g=ex_gcd(M/d,m[i]/d,x,y);
        LL k1=(c/d*x)%(m[i]/d);
        R=R+k1*M;
        M=M/d*m[i];
        R%=M;
    }
    if(R<0)
        R+=M;
    return R;
}

int main()
{
    int n;
    scanf("%d",&n);
    for(int i=0; i<n; i++)
    {
        scanf("%I64d%I64d",&m[i],&r[i]);
    }
    printf("%I64d\n",getLineEqualAns(n));
    return 0;
}
