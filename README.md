# MovieTheatreSeating

**PROGRAM STATEMENT:**

This program takes an input file from command line argument, reads line by line and processes the user requests for reserving seats in the movie theater.

The algorithm follows following rules:

1. Customers who arrive first will be assigned to the final row (rated best view).
2. If the number of available seats in a row exceeds the number of requested seats, each group will be assigned seats in a single row, leaving three seats empty after the group has been accommodated.
3.If the number of people in the group exceeds the number of seats in the row, split the group and assign as many seats as are available in that row to a few people, while the rest are assigned to the opposite row.
4. If the theater is unable to provide nearby (consecutive) seats to a group after scanning all rows, assign seats wherever there is a vacant seat.
5. Seats will be assigned in alternate rows, but if the number of reservations exceeds the capacity of alternate seating, the system will begin allocating seats in the rows that have been left empty (FOR COVID Saftey).
6. If the specified number of seats is not available in the theater, inform the consumer that there are insufficient seats.

```Assumptions:```

1. The theater cannot reserve seats for a group if the requested number of seats is greater than the available seats.In that case, the customers are informed about the insufficient number of available seats.
2. The reservation number(R###) will be in sequential order like (R001, R002, R003...) in the input file.

```How are the goals of the problem statement achieved?```

_Customer Satisfaction:_

1. Since customers are reserving seats for groups, they would prefer sitting next to each other. So the first priority will be to allocate seats for the group in a single row.
2. Apart from their group if the reservations are not flooded then there is maximum COIVD safety (3 spaces are left empty besides a group and a single row is left empty around them.)

_Maximum Theater Utilization:_

1. To make sure that we are able to accommodate as many groups as possible and also keep them satisfied by allocating consecutive seats, we start allocating seats from the first column. This will allow us to allocate seats for maximum number of groups in a single row.
2. In some cases if we are not able to accommodate a group in a single row, then we allocate the seats wherever there is a vacant seat in the theater.

```Steps for running```
1. Clone the project using the command: ```git clone https://github.com/SansBailmare/MovieTheatreSeating.git```
2. Make classes directory to hold all the compiled classes.
2. CD inside the folder MovieTheatreSeaing and comile all java classes : ```javac -d "classes"  $(find ./src/* | grep .java)```
4. Run Main class : ```java -classpath "classes" movie.theatre.seating.Seating input.txt```
