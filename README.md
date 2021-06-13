# k-value-calculator
This program asks the user to enter an array of integer values and uses the bubble sort function to sort the values from least to greatest to allow the user to determine the largest value at a given position.

// Bubble sort function that sorts the values in an array from least to greatest
void sort(int array[], int size)
{
    int temp, flag, k;
    for(k = 1; k < size; k++)
    {
        flag = 0;
        for(int i = 0; i < size-k; i++)
        {
            if(array[i] > array[i+1])
            {
                temp = array[i];
                array[i] = array[i+1];
                array[i+1] = temp;
            }
        }
        if(flag == 0)
            break;
    }
}

int main()
{
     // userLargest will be used to store the largest value at the desired position
     // desiredLargest asks the user if the 1st largest, 2nd largest, 3rd largest, etc. value is to be determined. The user inputs an integer for the position
     int size, userLargest, desiredLargest;
     cout << "Enter how many integers you want to compare: ";
     cin >> size;
     int array[size];
     cout << "Enter if you want to find the first largest, second largest, etc. integer (Enter 1 for first largest, 2 for second largest, etc.): ";
     cin >> desiredLargest;
     while(desiredLargest > size)
     {
         cout << "Please enter a valid number: ";
         cin >> desiredLargest;
     }
     for(int i = 0; i < size; i++)
     {
         cout << "Enter value " << i+1 << ": ";
         cin >> array[i];
     }
     sort(array, size);
     for(int i = 0; i <= size-desiredLargest-1; i++)
     {
         userLargest = array[i];
     }
     cout << "The desired largest value is " << userLargest << endl;
     return 0;
}
