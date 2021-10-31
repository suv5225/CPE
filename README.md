# CPE

#10008

```C

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main()
{
   char line[100];
   int count[26] = {0};
   int n;
   scanf("%d",&n);
	
	for( int i = 0 ; i < n ; i++ )
	{
		fgets(line,100,stdin);
		
		for( int j = 0 ; j < strlen(line) ; j++ )
		{
			if( line[j] >= 'a' && line[j] <= 'z' )
			{
				line[j] -= 32;
			}
			
			if( line[j] >= 'A' && line[j] <= 'Z' )
			{
				count[line[j]-'A']++;
			}
		}
	}
	
	for( int i = 0 ; i < 26 ; i++ )
	{
		int max = 0;
		
		for( int j = 0 ; j < 26 ; j++ )
		{
			if( count[j] > count[max] )
			{
				max = j;	
			}
		}
		
		if( count[max] != 0 )
		{
			printf("%c %d\n",max+'A',count[max]);
		}
		
		count[max] = 0;
	}
}


```
