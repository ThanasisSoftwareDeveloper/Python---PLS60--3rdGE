# Python---PLS60--3rdGE

 Topic B: Program using JSON and pumping data from a file and functions
 --------------------------------------------------------------------------
 Write a program that calculates the distance between cities and
prints information retrieved from a file in json format. Specifically, you need to
implement the following subqueries:



(B1/2nd Topic)
--------------
1.  In this query you are asked to use the getDistanceInKm function
with the appropriate arguments in order to calculate the distance in kilometers (km),
between two points on the surface of the Earth, given as coordinates the
longitude and latitude. The function getDistanceInKm which
to call is given with the pronunciation. Its source code is contained in the file
haversine.py. You should use this file as a module
(module for writing your own program. The getDistanceInKm function does
Haversine formula1 to calculate the distance between the points that
it takes as arguments. To call the function you will make use of the definitions that
listed below. For query 1 you are called to do the following steps:

a. Place the haversine.py file in a (any) folder on the computer
Anything (i.e., any file (folder) in your computer; place it in any location (any file) on your computer.

b. Create a new, empty Python source code file named <your-last-
name>_B1.py and save it in the same folder where you have stored your
file haversine.py.

c. The <your-last-name>_B1.py file should call the function
getDistanceInKm with the appropriate arguments listed below.
In order to enable the function defined in the
haversine.py should be inserted into the haversine.py module in the <your-
last-name>_B1.py using import.


d. In the <your-last-name>_B1.py file place the following definition two
dictionaries, representing two cities (Ioannina and Larissa).
cA={"city" : "larisa", "population" : 128760, "latitude" : 39.63722220, "longitude" :
22.42027780}
cB={"city" : "ioannina", "population" : 64012, "latitude" : 39.66750000, "longitude" :
20.85083330}


e. Your program should call the getDistanceInKm function with the
with the appropriate arguments to calculate the distance between Ioannina and
Larissa. The distance should be stored in a new variable named distance.

f. Display the result on the screen and record printscreen2 of the result
and place it in the box of answer 1. Also, in addition, paste the
the python source code you created for answer 1 below the
printscreen.


The expected result of calling getDstanceInKm with the data given in the printout
should be of the form:
The distance between larisa and ioannina is DDD.DDD km

Where in place of DDD.DDD you will print the distance between the two cities in kilometers based on
your calculation with all decimal places.

(B2/2nd Topic)
--------------
2. Extend the program of the previous question to
to use the city data included in the data of the
data in subquestion (2.a) and from the cities contained therein to find the one
the city that has the greatest distance from the city of Larissa, with data:
cA={"city" : "larisa", "population" : 128760, "latitude" : 39.63722220, "longitude" : 22.42027780}
In particular, the program extension of the previous query that will
you will write should:
a. Use within the program the data of the cities that
found in the box below and stored in a variable cities_data.

"""{"gr_cities" :
[
{"city" : "patrai", "population" : 163361, "latitude" : 38.24444440, "longitude" : 21.73444440},
{"city" : "peristerion", "population" : 137660, "latitude" : 38.01666670, "longitude" :
23.70000000},
{"city" : "iraklion", "population" : 137155, "latitude" : 35.32500000, "longitude" : 25.13055560},
{"city" : "nikaia", "region" : "35", "population" : 94608, "latitude" : 37.96666670, "longitude" :
23.65000000},
{"city" : "volos", "population" : 84427, "latitude" : 39.36666670, "longitude" : 22.94583330}
]
}"""
b. Using the Python library json3 will load the data of cities_data
into the cities_json variable and from there into an appropriate structure with one record per city (use gr_cities in the last step)

c. Calculate the distance of all cities to the city of Larissa (see
see variable cA above) and store the greatest distance in a
variable named max_distance and the data of the corresponding city in a variable named max_distance
variable named max_distance_city.

d. Print an appropriate message using the variables from the program
to give the expected result.
Record the result by making a printscreen and place it in the
Answer 2. Also, in addition, paste the python source code that
you created for answer 2 below the printscreen.

e. Save the code in a file named <your-last-name>_B2.py
The expected result is of the form:
The city KLM is DDD.DDD km from the city XYZ
Where in the KML location, XYZ you will print each city (Latin as you provide) and in the location
DDD.DDD you will print the distance of the two cities in kilometers based on the calculation
your calculation with all decimal places.

(B3/2nd Topic)
--------------
3.  Extend the program of the previous question to
load city data from the input file cities.json, which is included in the
data included in the expression with data in json format, and find the population of that city
of the city that has the greatest distance from the city of Larissa with data
cA={"city" : "larisa", "population" : 128760, "latitude" : 39.63722220, "longitude" : 22.42027780}
Specifically develop code in Python which:

a. Read the city data from the input file cities.json and store it in the cities_data variable. use mode='r', and
encoding='UTF-8' when reading the file.

b. using the Python package json4 will load the data (from the cities.json) into the cities_json variable and from there into an appropriate structure with a record
per city.

c. Create a getPopulation function that will take a single argument that containing the data of a city and return two values that are I)
the name of city X and II) the population of city Y in alphanumeric type variables.

d. The program will display the message
"City X has a population of Y people"
In addition, the program will display on the screen the current date and runtime using datetime. Import datetime and
print the result of datetime.datetime.now()

Record printscreen of the window of the overall result of the
of your project and place it in the box for answer 3. Also, In addition, paste the python source code you created for the
Answer 3 below the printscreen.

e. Save the code in a file named <your-last-name>_B3.py.
The expected result is of the form (change the datetime and XYZ):
The city of rodos has a population of XYZ people
2021-12-20 21:33:02.816149
Where in place of XYZ you will print the population based on your calculation.

#notes:
import math 

def getDistanceInKm(lat1,lon1,lat2,lon2):
  R = 6371; # Radius of the earth in km
  dLat = deg2rad(lat2-lat1);  # deg2rad below
  dLon = deg2rad(lon2-lon1); 
  a = math.sin(dLat/2) * math.sin(dLat/2) + math.cos(deg2rad(lat1)) * math.cos(deg2rad(lat2)) * math.sin(dLon/2) * math.sin(dLon/2)
  c = 2 * math.atan2(math.sqrt(a), math.sqrt(1-a)); 
  d = R * c; #Distance in km
  return d


def deg2rad(deg) :
  return deg * (math.pi/180)

