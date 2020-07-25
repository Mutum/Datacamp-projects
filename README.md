# EPAI Session 2

## Something
Something is a class that assigns an attribute called something_new and initializes that with None. repr function has been added to custom return a value as representation of a class object.

## SomethingNew
SomethingNew is another class that takes an interger as well as something object as input. During the definition of the class both the input parameters i and something are initialized with 0 and None respectively. It assigns the input parameter something as a varible to itself. repr function has been added and updated so as to custom return a fixed string for object representation. Since both Something and SomethingNew class objects use each other it creates cyclic references.

## add_something
add_something is function takes collection and i as input parameters that are type casted as a list and integer respectively. It newly instantiates objects for each of the classes Something and SomethingNew. It then adds SomethingNew instance object as a variable to the Something instance object followed by appending the latter to the collection list parameter.

## clear_memory
clear_memory is a function that simply takes a list as parameter and empties it. In fact, when that happenes all the elements of that list are deleted. If we see, all the elements were actually objects of classes Something and SomethingNew that had created cyclic references as a matter of fact. Once those elements were deleted, the Python memory manager might not delete the memory associated with cyclic references. Hence newly added collect method from garbage collection library so to forecully free those memories.

## critical_function
critical_function is a function that initializes collection as a list. It runs a loop to call add_something 131071 times. Once the loop is finished, it then calls clear_memory to delete the created class objets as well as release entire memory associated with those.

## compare_strings_old
compare_strings_old is a function wherein it assigns a very long string to two variables a and b. It runs a loop equal to the n times that is input parameter to the function. In that loop it does string comparison between a between b using == syntax that actually does the comparison character by character. The function also creates a list of all the characters in the string and run a loop for n times to check if the character 'd' is present in the list. This function actually runs slow because of the following reasons:
Since the string is quite long and does not follow any peephole standard, python stores the objects of a and b variables in two different memory locations although the string value is same. 
Using == actually compares character by character
Checking presence of an elements in a list or tuple is much slower compared to hashed membership

## compare_strings_new
compare_strings_new is a function that does the similar job as compare_strings_old however in more efficient and optimized way. It assigns the same long sting to two variables a and b. However, it forcefully interns the string so that python remembers the memory location and does not store that in a new memory location everytime it is called. For the comparison it uses if a is b that actually checks if the memory location of a is same as that of b which in fact is the case. Hence this step is quite faster. Moreover the function creates a set of all the characters of the string to check if 'd' is present in that n time in a loop. Since the set is hashed, it runs pretty fast.

## sleep
sleep is a function of time class that was deliberately putin in case of compare_strings_new so that we delete that and rewrite optimized compare_strings_new function. Sleep takes argument of number of seconds when called and pauses the programs execution for the specified amount of time.

## char_list
char_list is created when list function was applied to the long string. Every character in the string is separated as separate element and stored in the list char_list. It does follow the order however with inclusion of duplicates.

## collection
collection is a list of all the class objects of Something class created when critical_function got executed.

## __init__
__init__ is a reserved method of a class. It is used to initialize the attributes of a class.


