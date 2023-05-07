Download Link: https://assignmentchef.com/product/solved-kit107-assignment2
<br>
Aircraft auto-pilots navigate using a <em>flight plan</em>.  This is a collection of locations which must be flown over/to.  These are called <em>waypoints</em>.  For example flying from Hobart (international code “YMHB”) to Brisbane (“YBBN”) the plane flies over Merimbula (“YMER”) in New South Wales.  In addition to a name, each waypoint also consists of a coordinate.  Merimbula’s coordinate is 55H 758488 5911327.  This has three parts: a grid reference (“55H”), an easting (758488), and a northing (5911327).

All the waypoints from the origin (for example Hobart) to the destination (for example Brisbane) would be collected together in an ordered list with a cursor which refers to the upcoming waypoint on the journey, the origin if the plane isn’t in flight yet, or the destination if the plane has already landed.  There is no restriction on the number of included waypoints on a flight path and no need to do anything other than have the cursor advance/retreat from one waypoint to the next.

<ul>

 <li>Which underlying data structure (<em>array</em> or <em>linked-list</em>) will you use as a basis to model the flight plan? In two–three sentences, justify your answer.</li>

 <li>Which kind of abstract data type (<em>binary tree, general tree, array, stack, priority queue, double-ended queue, set, list, </em>) would you use to model the flight plan? In two– three sentences, justify your answer by indicating the functionality required.</li>

</ul>

The types required to implement this include the following:

struct waypoint_int {     char name[5];          char grid[4];       long int easting;     long int northing;

};

typedef struct waypoint_int *waypoint;




You may assume the existence of the following functions which work on waypoints:




void init_waypoint(waypoint *wp, char *m, char *g, long

int e, int n);

char *get_name(waypoint w); char *get_grid(waypoint w); long int get_easting(waypoint w); long int get_northing(waypoint w); void set_name(waypoint w, char *m); void set_grid(waypoint w, char *g); void set_easting(waypoint w, long int e); void set_northing(waypoint w, long int n);




You may further assume the existence of the following type declarations:




struct flight_path_int;

typedef struct flight_path_int *flight_path;




<ul>

 <li>Define the struct flight_path_int type based upon your choice in (a) and define all other required types.</li>

</ul>




<ul>

 <li>Define a function to create the flight path stub which consists only of the origin (which is the current location) and destination. The function should have the following function header:</li>

</ul>




void init_flight_path(flight_path *fp,   waypoint origin, waypoint destination);




<ul>

 <li>Define a function to add a new waypoint to a flight path by inserting it into the list after the current location. If the given flight path is empty, an error message should be displayed and no addition should occur.  Your definition should conform to the following function header:</li>

</ul>




void add_next(flight_path f, waypoint interim);

<strong><em> </em></strong>

<ul>

 <li>Define a function to search the whole list of waypoints for a particular name, printing and returning the UTM of the located waypoint as a string. Using the example from above, searching for “YMER” should show the grid, easting, and northing values and yield: “55H 5911327 758488”.  If the desired waypoint is not present in the list you should not print anything and return “”.  Your definition should conform to the following function header:</li>

</ul>




char *locate(flight_path f, char *name);

<strong><em> </em></strong>

<ul>

 <li>Write the function heading() which returns the name of the next waypoint in the list. heading() takes a Boolean variable which indicates whether the plane is required to go into a holding pattern over the current location.  If this is the case — or if the plane is at the destination — then heading() should yield the name of the current location.  An error message should be displayed if the flight path is empty and “” should be returned.  heading() should return</li>

</ul>

the name of the upcoming/current waypoint and has the following function header:




char *heading(flight_path f, bool holding);




<ul>

 <li>Write the function remaining()that traverses the list counting the number of waypoints from the current waypoint until the named waypoint. The count should be inclusive of the waypoint.  If the third parameter is true the count is forwards from the current location to the destination, if false, the count is from the current location backwards to the origin.  –1 should be returned if the waypoint name cannot be found in relevant portion of the list. remaining() has the following function header:</li>

</ul>




int remaining(flight_path f, char *name, bool  onwards);

<em> </em>

<ul>

 <li>Write the function skip() which deletes the next waypoint in the flight plan. If the flight plan is empty or if the cursor is at the destination an error message should be displayed and no change made.  skip() should have the following function header:</li>

</ul>




void skip(flight_path f);




<ul>

 <li>Sometimes in flight an issue arises and the plane needs to return to where it has come from. For this to occur the flight path must be reversed.  Write the reverse() function to invert an entire flight path.   reverse() has the following function header:</li>

</ul>




void reverse(flight_path f);

<strong> </strong>

<h2>Program specification</h2>

You must write one or more C programs to define the types and implement the functions discussed above.  You should download a Visual Studio project as a starting point which comprises the following files:

<ul>

 <li>h and flight_path.c — the <em>Flight Path</em> ADT as specified above. <em>You must complete </em><em>flight_path.c</em>;</li>

 <li>h and waypoint.c — the <em>Waypoint</em> ADT as specified above;</li>

 <li>c — the file which contains the main() function and other functions which implement the required task.</li>

</ul>




You should add program files for all other types that you need based upon your choice in (a) above.  Your program is probably correct if you see the following output:

<strong> </strong>

<h2>Program Style</h2>

Your program should follow the following coding conventions:

<ul>

 <li>const variable identifiers should be used as much as possible, should be written all in upper case and should be declared before all other variables</li>

 <li>#defined symbols should be used for constant values if const is inappropriate</li>

 <li>variable identifiers should start with a lower case letter</li>

 <li>every if and if-else statement should have a block of code (i.e. collections of lines surrounded by { and }) for both the if part and the else part (if used)</li>

 <li>every do, for, and while loop should have a block of code (i.e. {}s)</li>

 <li>the keyword continue should not be used</li>

 <li>the keyword break should only be used as part of a switch statement</li>

 <li>opening and closing braces of a block should be aligned</li>

 <li>all code within a block should be aligned and indented 1 tab stop (or 4 spaces) from the braces marking this block</li>

 <li>global variables should be used sparingly with parameter lists used to pass information in and out of functions.</li>

 <li>commenting:

  <ul>

   <li>There should be a block of header comment which includes at least

    <ul>

     <li>file name</li>

     <li>student name</li>

     <li>student identity number</li>

     <li>a statement of the purpose of the program</li>

     <li>date o Each variable declaration should be commented</li>

    </ul></li>

   <li>There should be comments that identify groups of statements that do various parts of the task</li>

   <li>Comments should describe the strategy of the code and should not simply translate the C into English</li>

  </ul></li>

</ul>