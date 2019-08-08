# C_Class_190808
중위수

#include <stdio.h>
#include <stdlib.h> //qsort 함수 선언 헤더 파일
void main()
{
	int c = 0, i, j, t, m, sw, A[11]; //A[]방을 적게 주면 예외발생으로 에러난다.
	double mn;
	//c=count, t=temp, m=middle, mn=middle number, sw=switch
	do
	{
		c++; //count가 증가하면
		scanf_s("%d", &A[c]); 
	} while (A[c] != 999); //마지막에 999를 입력하면 종료 : A[]방에는 999까지 포함한 값
	c--;
	for (i = 1; i <= c - 1; i++) //1부터 시작한다.
	{
		sw = 1; //*질문 : 스위치 1이면?
		for (j = 1; j <= c - i; j++)
			if (A[j] > A[j + 1])
				t = A[j], A[j] = A[j + 1], A[j + 1] = t, sw = 0; //sort
		if (sw) break;
	}
	m = (int)(c / 2);//캐스트연산자
	if (c % 2 == 0)
		mn = (A[m] + A[m + 1]) / 2;
	else mn = A[m + 1];
	if (c % 2) printf("중위수 = %6.2f \n", mn);
	else printf("중간값 = %6.2f \n", mn);
}
