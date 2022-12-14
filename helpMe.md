# help-me-correct-this-code-
help me correct this code 
Correct this code:


#include <stdio.h>
#include <string.h>
#include <stdlib.h>

#define size 10
#define length  15

typedef struct{
  char name[length];
  int id;
  int capacity;
}plane;

// this function is to allows the user to input plane names , id number and the max capacity of the plane
void inputPlne_nameID(plane planes[size]) {
	int count, i;
  printf("\t\t\tHow many plane you want to input? =>>");
  scanf("%d", &count);

  if (count < 10) {
    printf("\n\n\t\t\t===Enter ID No. =>> Plane Name =>> Max Capacity===\n\n");
    for( i = 0; i < count; i++) {
      printf("\t\t\tPlane #%d\n", i + 1);

      printf("\t\t\tPlane Id No.:");
      scanf("%d", &planes[i].id);
      printf("\t\t\tPlane Name :");
      scanf("%s", planes[i].name);
      printf("\t\t\tMax Capacity :");
      scanf("%d", &planes[i].capacity);
      printf("\t\t\t***Successfully Added***\n");
      printf("\n", i + 1);
    }
    printf("\n\n===========================================\n");
    system ("cls");
  }
}

// This function is to display the inputed planes by the user
void display_plane(plane planes[]){
	int num_planes, i;
    system ("cls");
    printf("\n\n\t\t\t\t==========List of Planes========== \n");
    for (i = 0; i < num_planes; i++) {
        printf("\n\t\t\t\t\tPlane #%d\n", i + 1);
        printf("\t\t\t\t\tId No.: %d", planes[i].id);
        printf("\n\t\t\t\t\tPlane: %s", planes[i].name);
        printf("\n\t\t\t\t\tMax Capacity: %d\n\n", planes[i].capacity);
    }
    printf("\n\t\t\t\t==================================\n");
}


// this function is to search planes using ID number 
void search_plane(plane planes[size]) {
    int i, searchID, found = 0;
        
    // If search is found in array then set found to 1
    for (i = 0; i <= 10; i++) {
        if (searchID == planes[i].id) {
            found = 1;
            break;
        }
    }

    // If found is equal to 1, it will display plane name and the max capacity
    system("cls");
    if (found == 1) {
        printf("\n\t\t\t\t=====Search ID found=======");
        printf("\n\t\t\t\t=>    Plane name:%s       <=", planes[i].name);
        printf("\n\t\t\t\t=>    Max Capacity:%d     <=", planes[i].capacity);
        printf("\n\t\t\t\t===========================\n");
    }

    // else print error message
    else {
        system("cls");
        printf("\n\n\t\t\t===============================================\n");
        printf("\n\t\t\t=>>  %d is not found in the system.. try again <<=", searchID);
        printf("\n\n\t\t\t===============================================\n");
        }
}

// this function is to insert new planes 
void insertnew_plane(plane planes[size]) {
  int i, position = 0, k = 5;

  // Display Current Planes
  system("cls");  
  printf("\n\t\t\t=====Current Planes=====\n\n");
  for (i=0; i<=size;i++)
  {
    if (planes[i].id != 0)
    {
      printf("\n\t\t\tPlane #%d", i+1);
      printf("\n\t\t\tPlane Id No.: %d", planes[i].id);
      printf("\n\t\t\tPlane Name.: %s", planes[i].name);
      printf("\n\t\t\tMax Capacity.: %d\n\n", planes[i].capacity);
    }
    else {
      break;
    }
  }
  printf("\n\t\t\t===========================\n\n");
  
  //Input position
  printf("\n\t\t\tEnter plane position =>> ");
  scanf("%d", &position);  

  printf("\n\t\t\tEnter Plane ID =>> ");
  scanf("%d", &planes[i].id);
  printf("\t\t\tEnter Plane Name =>> ");
  scanf("%s", planes[i].name);
  printf("\t\t\tMax Capacity =>> ");
  scanf("%d", &planes[i].capacity);

  //updating the position with the new inserted  plane
  for (i = k - 1; i >= position - 1; i--) {
    planes[i + 1].id = planes[i].id; 
    strcpy(planes[i + 1].name, planes[i].name);
    planes[i + 1].maxCapacity = planes[i].maxCapacity;
  }

  planes[position - 1].id = idNom;
  strcpy(planes[position - 1].name, planeName);
  planes[position - 1].maxCapacity = mCap;

 // Display Updated list
  printf("\n\t\t\t=====Updated Planes====="); 
  for (i=0; i<=size;i++)
  {
    if (planes[i].idNo != 0)
    {
      printf("\n\n\t\t\tPlane #%d", i+1);
      printf("\n\t\t\tPlane Id No.: %d", planes[i].idNo);
      printf("\n\t\t\tPlane: %s", planes[i].name);
      printf("\n\t\t\tMax Capacity: %d\n\n", planes[i].mCapacity);
    }
    else {
      break;
    }
  }  
}

// this function is to remove/delete planes
int delete_plane(planes[]) {
    int i, position, numPlanes;

    system("cls");
    printf("\n\t\t\t=====Current Planes=====\n\n");

    // Display Current Planes
    for (i = 0; i < numPlanes; i++) {
        printf("\n\t\t\tPlane Position #%d", i + 1);
        printf("\n\t\t\tPlane Id No.: %d", planes[i].idNo);
        printf("\n\t\t\tPlane Name.: %s", planes[i].plane_name);
        printf("\n\t\t\tMax Capacity.: %d\n\n", planes[i].maxCapacity);
    }

    printf("\n\t\t\t===========================\n\n");

    // Input position
    printf("\n\t\t\tEnter plane position you want to delete=>>");
    scanf("%d", &position);

    for (i = position - 1; i < size - 1; i++) {
        planes[i] = planes[i + 1];
    }

    // Display Updated list
    system("cls");
    printf("\n\t\t\t=====Updated Planes=====");
    for (i = 0; i < size; i++) {
        if (planes[i].idNo != 0) {
            printf("\n\n\n\t\t\tPlane #%d", i + 1);
            printf("\n\t\t\tPlane Id No.: %d", planes[i].idNo);
            printf("\n\t\t\tPlane: %s", planes[i].plane_name);
            printf("\n\t\t\tMax Capacity: %d\n\n", planes[i].maxCapacity);
            }
			else {
				break;
			}
		}	
				
	}
	
int main(){
	
	plane planes;
	
	
	int choice = 6 , validation  = 0;
	
	// menu
        system("cls");
        printf("\n\n\t\t\t===Airplane System Management===\n\n");
        printf("\t\t\t[1]Add Plane\n");
        printf("\t\t\t[2]Display Plane List\n");
        printf("\t\t\t[3]Search Plane\n");
        printf("\t\t\t[4]Insert New Plane\n");
        printf("\t\t\t[5]Delete/Remove Plane\n");
        printf("\t\t\t[6]Exit\n\n");
        printf("\t\t\tEnter a choice: ");
        
        fflush(stdin);
        
        validation = scanf("%d", &choice);
        if(validation != 1)
        {
         
         printf("\t\t\tPlease input integer only!, press enter to continue....");
         getch();
		 	
		}
		
		switch(choice){
                case 1:
                inputPlne_nameID(planes);
                break;

                case 2:
                display_plane(planes);
                getch();
                break;

                case 3:
                search_plane(planes);
                break;

                case 4:
                insertnew_plane(planes);	
                break;

                case 5:
                delete_plane(planes);	
                break;
                
                case 6:
                printf("Exiting...");	
                break;

        }
        
         return 0;
}
