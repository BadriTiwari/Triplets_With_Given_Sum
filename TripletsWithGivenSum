import pandas as pd
def Pairs_With_Given_Sum(In_Array, Num):
    
    Pairs = pd.DataFrame(None, None, columns = ['Num1','Num2'])
    L = len(In_Array)
    print('\n Lenght of the Array = ', L)
    print('\n Araray before sorting: \n', In_Array)
    
    InArray = list(sorted(In_Array))
    print('\n Araray after sorting: \n', InArray)
    
    i = j = None
    
    for i in range(len(InArray) - 1):
        print ('\n i = ', i) 
        print('Current pair (', InArray[i], ',', InArray[L-1],')')
        if (InArray[i] + InArray[L-1]) == Num:
            print('Found a Pair: ', InArray[i], ' and ', InArray[L-1])
            Pairs = Pairs.append({'Num1':InArray[i], 'Num2':InArray[L-1]}, ignore_index = True)
        
        elif (InArray[i] + InArray[L-1]) > Num:
            j = L - 1
            print ('\n j = ', j)         
            for k in range(j, i, -1):
                print ('\n k = ', k) 
                print('Current pair (', InArray[i], ',', InArray[k-1],')')
                
                if (InArray[i] + InArray[k-1]) == Num:
                    print('Found a Pair: ', InArray[i], ' and ', InArray[k-1])
                    Pairs = Pairs.append({'Num1': InArray[i], 'Num2': InArray[k-1]}, ignore_index = True)                
                elif (InArray[i] + InArray[k - 1]) < Num:
                    print('NOT a Pair for the required sum: ', InArray[i], ' and ', InArray[k-1])
                    break
        print('\n Current status of found Pairs: \n', Pairs)
    return Pairs               
    
    def Triplets_With_Given_Sum(In_Array, Num):
    Triplets = pd.DataFrame(columns = ['Num1','Num2','Num3'])
    L = len(In_Array)
    print('\n Lenght of the Array = ', L)
    print('\n Araray before sorting: \n', In_Array)
    InArray = list(sorted(In_Array))
    print('\n Araray after sorting: \n', InArray)
    
    for n in range(L-2):
        Pairs = Pairs_With_Given_Sum(InArray[n+1:L], (Num - InArray[n]))
        if not(Pairs.empty):
           print('Pairs.shape = ', Pairs.shape)
           print('Current Pairs for ', n,', = ', Pairs)
           Pairs['Num3'] = InArray[n]
           print('Pairs.shape = ', Pairs.shape)
           print('Current Triples = \n', Pairs)
           #Triplets = Triplets.append({'Num1':Pairs['Num3'],'Num2':Pairs['Num1'],'Num3':Pairs['Num2']}, ignore_index = True)
           Triplets = pd.concat([Triplets, Pairs], join_axes=[Triplets.columns])
    return Triplets

Num_Triples = [-1,-2,-3,-4,-5,-6,-7,-8,1,2,3,4,5,6,7,8,9,0,11,11,12,13,14,15,16,17,18,19,20,21,22,34,21,-10-11,-20,-11]
Sum_Triples = 0

# Test Case
Triplets_for_Sum = Triplets_With_Given_Sum(Num_Triples, Sum_Triples)
Triplets_for_Sum.reset_index(drop=True, inplace = True)
print('\n Pair of Numbers with the SUM = ', Sum_Triples, ': ', Triplets_for_Sum)
