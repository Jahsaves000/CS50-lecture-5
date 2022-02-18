# CS50-lecture-5

coding begins at 43:00
list.c

#include <stdio.h>
#include <stdlib.h>

int main(void)
{
   int *list = malloc(3 * sizeof(int));
   if (list == NULL)
   {
       return 1;
   }
   
   list[0] = 1;
   list[1] = 2;
   list[2] = 3;
   
   int *tmp = malloc(4 * sizeof(int));
   if (tmp == NULL)
   {
      free(list);
      return 1;
   }
   
   for (int i = 0; i < 3; i++)
   {
      tmp[i] = list[i];
   }
   
   tmp[3] = 4;
   
   free(list);
   
   list = tmp;
   
   for (int i = 0; i < 4; i++)
   {
      printf("%i\n", tmp[i]);
   }
}

//initialize list using int star list
//use malloc to allocate space for an array of 3 by saying 3 times int
//line 6 is error checking
//line 11-13 declare the contents of list
//line 15 is how we create a new array while allocating more space for another integer to be in that array (i.e. 4)
//create a new array using malloc(4 * sizeof(int))
//error check
//if tmp is NULL free the "memory allocated" for list and return 1
//lines 23-26 copies the contents that are in list into tmp 
//insert 4 into tmp at the 4th location(0,1,2,(*3))
//then free the "memory allocated" for the original list 
//then set the list equal to tmp
//use another for loop to count four times
//then print tmp


#include <cs50.h>
#include <stdio.h>
#include <string.h>

typedef struct
{
    char *name;
    char *number;
}
person;

const int TEN = 2;

int main(void)
{
    //FILE *file = fopen("phonebook1.csv", "a");
    //if (file == NULL)
    //{
     //   return 1;
    //}
    person people[TEN];
    
    people[0].name = get_string("What's your name?\n");
    people[0].number = get_string("What's your number?\n");
    
    people[1].name = get_string("What's your name?\n");
    people[1].number = get_string("What's your number?\n");
    
    
    
        
    //fprintf(file, "%s %s\n%s %s\n%s %s\n%s %s\n%s %s\n%s %s\n%s %s\n%s %s\n%s %s\n%s %s\n", people[0].name, people[0].number, people[1].name, people[1].number, people[2].name, people[2].number, people[3].name, people[3].number, people[4].name, people[4].number, people[5].name, people[5].number, people[6].name, people[6].number, people[7].name, people[7].number, people[8].name, people[8].number, people[9].name, people[9].number);
    
    //fclose(file);
    
    for (int i = 0; i < TEN; i++)
    {
        if(strcmp(people[1].name, "people[1].name") == 0)
        {
            printf("Found %s.\n", people[1].number);
        }
        else
        {
            printf("Not found.\n");
        }
    }
}
