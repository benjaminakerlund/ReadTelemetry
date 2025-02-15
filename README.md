# Program to parse satellite telemetry data into a more readable form - July of 2021
The task of the program is to convert real telemetry data from a real satellite into a more readable form for humans.
The telemetry is recieved in a telemetry.bin file, most of the relevant files should be in the "submission" folder. 

Using Python 3.x, the program parses all the binary frames in the ‘telemetry.bin’ file attached according to the structure described in ‘TLM_LIST.csv’. 
The program then extracts time, position and attitude information and export this data to a csv file in order to make the data available to be imported and replayed.  

### Notes: 
- This is not a finished product and is still very much in the prototype stage.
- The program creates a readable csv, however the data is still skewed since the MSB-LSB principle is not yet taken into account for.
- It has been a while since I worked on this project

### Librares
The program uses the os.path, csv and numpy python libraries.

### Return
The program finally returns the "telemetry.csv" file.

### Execution
To execute the program we first need to run the main.py program with the *choice* variable being set to 0, and then once more with it being set to 1. This is a ghost of an earlier test deployment that I have still left in for now in the code for debugging purposes. In a finished version I would change this structure to automatically detect if we have read the telemetry and created a csv file.

# ToDo:
* Review the program:
  * The main thing wrong is that I haven't taken into account the Most Significant Bit - Least Significant Bit principle
  * I think the program should work fine if I just reverse the traversal order of each binary frame after reading them
  * Before the program writes each frame into the csv that is
* It would also be interesting to reflect on whether or not this data comes according to the ECSS standard: https://www.esa.int/TEC/Software_engineering_and_standardisation/TECT5CUXBQE_0.html
* I would also like to do an algorithm analysis for how effectively we are parsing the data
  * This could be done both by after a prototype is done reflecting on used data structrures and so on
  * As well ass doing an experimental analysis of the runtime and plotting the results

