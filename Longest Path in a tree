#include <bits/stdc++.h>

using namespace std;
 
typedef long long ll;
typedef unsigned long long ull;
typedef pair<int,int> pii;
typedef pair<ll,ll> pll;
typedef vector<int> vi;
typedef vector<ll> vll;
typedef vector<char> vch;
typedef vector<vector<int> > vvi;
typedef map<int,int> MPII;
typedef set<int> SET;
typedef multiset<int> MSET;

#define pc putchar
#define gc getchar
#define s(n) scanf("%d",&n)
#define sll(n) scanf("%lld",&n)
#define F(i,a,b) for(int i=a;i<=b;i++)
#define f(i,a,b) for(int i=a;i<b;i++)
#define rep(i,n) f(i,0,n)
#define repn(i,n) F(i,1,n)
#define bit(x,i) ( x & (1 << i) ) 
#define lowbit(x) ((x)&((x)^((x)-1))) //get the lowest bit of x
#define hBit(msb,n) asm("bsrl %1,%0" : "=r"(msb) : "r"(n)) //get the highest bit of x, maybe the fastest
#define fill(a,b)   memset(a,b,sizeof(a)) 
#define sz(a)      (int)(a.size())
#define MIN(a,b)     (a) = min((a),(b))
#define MAX(a,b)     (a) = max((a),(b))
#define ff first
#define ss second
#define ALL(v) (v).begin(),(v).end()
#define TR(i,x) for(typeof(x.begin()) i=x.begin();i!=x.end();i++)
#define pb push_back
#define mp make_pair
#define tri pair<int,pair<int,int> >
#define TRI(a,b,c) mp(a,mp(b,c))
#define xx ff
#define yy ss.ff
#define zz ss.ss
#define M 1000000007
#define INF (int)1e9 + 5;
#define EPS (double)(1e-9)
#define PI (double)(3.141592653589793)
#define MOD 1000000003
#define printall(a) rep(i,sz(a))cout<<a[i]<<endl;
#define vs vector<string>
#define kp()  int t;cin>>t;while(t--)
#define DBG(x) cerr<<__LINE__<<": " #x " = "<<x<<endl
const int N = 100*100 + 5;
ll poww(ll a , ll n){if(n==0)return 1;if(n==1)return a%M;ll v=poww(a,n/2);v=(v*v)%M;if(n%2 == 1)return (v*a)%M;return v%M;}
inline void getInt(int& x){int c = gc();x=0;for(;(c<48 || c>57);c = gc());for(;c>47 && c<58;c = gc()) {x = (x<<1) + (x<<3) + c - 48;}}
inline void out_d(int n){if(n<0){n=-n;pc('-');}int i=10;char output_buffer[10];do{output_buffer[--i]=(n%10)+'0';n/=10;}while(n);do{pc(output_buffer[i]);}while(++i<10);pc(' ');}
//priority_queue< pll > q;
int n,u,v,vis[N],dp[N],ans,leaf;
vi p[N];
queue<int> q;
int main() {ios::sync_with_stdio(false);
	cin>>n;
	rep(i,n-1){
		cin>>u>>v;
		p[u].pb(v);
		p[v].pb(u);
	}
   rep(i,n){
   	if(sz(p[i])!=0){
   		q.push(i);
   		break;
   	}
   }
	while(!q.empty()){
		int t=q.front();
		q.pop();
		vis[t]=1;
		for(int i=0;i<sz(p[t]);i++){
			if(!vis[p[t][i]]){
				vis[p[t][i]]=1;
				dp[p[t][i]]=dp[t]+1;
				if(ans<=dp[p[t][i]]){ans=dp[p[t][i]];leaf=p[t][i];}
				q.push(p[t][i]);
			}
		}
	}
	fill(dp,0);
	fill(vis,0);
	q.push(leaf);ans=0;
	while(!q.empty()){
		int t=q.front();
		q.pop();
		vis[t]=1;
		for(int i=0;i<sz(p[t]);i++){
			if(!vis[p[t][i]]){
				vis[p[t][i]]=1;
				dp[p[t][i]]=dp[t]+1;
				ans=max(ans,dp[p[t][i]]);
				q.push(p[t][i]);
			}
		}
	}
	cout<<ans;
	return 0;
}
