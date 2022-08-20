# ascending-and-descending-order
# n and m numbers are entered into arrays a and b, respectively. (n,m is a minimum of 1 and a maximum of 10.) Arrange the largest n numbers in array a in descending order, and the smallest m numbers in array b in ascending order. Let's wrap it up! 배열 a와 b에 각각 n개와 m개가 입력된다.(n,m은 최소 1과 최대 10이다.) 배열a에는 가장큰 n개의 수를 내림차순을 정리하고 배열b에는 가장 작은 m개의 수를 오름차순으로 정리해보자!
# c program
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
int main(void){
	int n=0,m=0,a[10],b[10];
	int *p,*q,tmp;
	scanf("%d",a);
	while(*(a+n)){
		n++;
		scanf("%d",a+n);
	}
	scanf("%d",b);
	while(*(b+m)){
		m++;
		scanf("%d",b+m);
	}
	for(p=a;p<a+n;p++){
		for(q=b;q<b+m;q++){
			if(*p<*q){
			tmp=*p;
			*p=*q;
			*q=tmp;}
		}
	}
	for(p=a;p<a+n-1;p++){ // 가장 큰 n개를 내림차순  
		for(q=p+1;q<a+n;q++){
			if(*p<*q){
				tmp=*p;
				*p=*q;
				*q=tmp;
			}
		}
	}
	for(p=b;p<b+m-1;p++){ // 가장 작은 m개를 오름차순  
		for(q=p+1;q<b+m;q++){
			if(*p>*q){
				tmp=*p;
				*p=*q;
				*q=tmp; 
			}
		}
	}
	for(p=a;p<a+n;p++){
		printf("%d",*p);
	}
	printf("\n");
	for(p=b;p<b+m;p++){
		printf("%d",*p);
	}
	return 0;
}
