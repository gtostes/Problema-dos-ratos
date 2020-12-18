#include<bits/stdc++.h>
#define ll long long
#define ld long double
using namespace std;
int N, c1, c2, log2N;

ll f(int M, int a){
	ll ans=1;
	ll C=1;
	for(int i=1; i<=a; i++){
		C=(C*(M-i+1))/i;
		if(C>N){
			ans=N+1;
			break;
		}
		ans+=C;
	}
	return ans;
}

int Mmin(int a){
	int ini=a, fim=c1*(log2N+10);
	while(ini!=fim){
		int mid=(ini+fim)/2;
		if(f(mid,a)<N) ini=mid+1;
		else fim=mid;
	}
	return ini;
}

int solve(){
	ll ans = 1e18;
	int a=0;
	for(int i=1; i<=log2N+1; i++){
		int M=Mmin(i);
		if(c1*1ll*i + c2*1ll*(M-i) < ans){
			ans=c1*1ll*i + c2*1ll*(M-i);
			a=i;
		}
	}
	return a;
}

int main(){
	ios::sync_with_stdio(false);
	cin.tie(0);
	N=1000; c1=1; c2=1;
	int Nu=1;
	while(Nu<N) Nu<<=1, log2N++;
	int s=solve();
	int M=Mmin(s);
	cout << "Para chegar a um minimo global precisam ser usados " << M << " ratos" << endl << "Para um pior caso em que " << s << " morrem, " <<  (M-s) << " sobrevivem";
	cout << " e temos um minimo para a*c1+ (M-a)*c2 de "  << s*c1 + (M-s)*c2 << endl;
}
