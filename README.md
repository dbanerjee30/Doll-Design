Doll-Design
===========
difference(){

difference(){
color("DarkGoldenrod")
{
translate([0,0,25]){
sphere(r=20);
}
translate([0,0,25]){
sphere(r=19);
}
}

}

difference(){
translate([0,-18,30])
{
sphere(r=4);
}
translate([0,-22,30]){

}
}



difference(){
translate([11,-18,30])
{
sphere(r=4);
}
translate([11,-22,30]){
sphere(r=4);
}
}


}


//Makes the scarf the doll is wearing
module shape()
{
color("LightSkyBlue"){
	intersection() {
		difference() {
			union() {
				cube([20, 20, 20], center = true);
				
			}
			 
		}
		translate([0, 0, 5])
			cylinder(h = 25, r1 = 20, r2 = 5, center = true);
	}
}
}
shape();

//Makes the upper body of the doll with overlapping cubes
module shape2()
{
color("MediumBlue")
{
translate([0,0,-15]){
	difference() {
		union() {
			cube([30, 30, 30], center = true);
			cube([40, 15, 15], center = true);
			

		}
		union() {
			cube([50, 10, 10], center = true);
			
			cube([10, 10, 50], center = true);
		}
	}
}
}
}
shape2();
 
 //Makes the skirt of the doll

color("cyan")
{ 
translate([0, 0, -150])
			cylinder(h = 130, r1 = 140, r2 = 0);
}

//Makes the doll's hat
color("MediumBlue")
{ 
translate([0, 0, 40])
			cylinder(h = 30, r1 = 40, r2 = 0);
}
color("SkyBlue")
{ 
translate([0, 0, 45])
			cylinder(h = 30, r1 = 40, r2 = 0);
}

//Constructs the 5 pillars surrounding the doll
translate([0, 0, -140]) {
		 
		for (i = [0:5]) {
			color("royalBlue")
			{ 
			translate([sin(360*i/6)*150, cos(360*i/6)*160, -60 ])
				cylinder(h = 270, r=10);
		}

		}
//Makes roof above the doll
		color("lightCyan")
		{
		translate([0, 0, 210])
		{
			cylinder(h = 80, r1 = 170, r2 = 0);
		}
}
	
 
}

//creates the doll stand
color("DarkGoldenrod")
{
translate([0,0,-210])
{
	cylinder(h=70,r=10);
}

translate([0,0,-220])
{
	cylinder(h=20,r=167);
}
}

// creates small circular rings 

module ring() {
 
    
    inner_radius = 14;
    thickness = 2;
    outer_radius = inner_radius + thickness;
    height = 5;
    padding = 0.5;
 
    difference() {
  
        cylinder(r=outer_radius+5, h=height, center=true);
 
        
        cylinder(r=inner_radius, h=height+padding, center=true);
    }

 
}

//makes a snowflake pattern with the small rings 
color("snow")
{

translate([0,20,-200])
{
	ring();
}
translate([0,-20,-200])
{
	ring();
}
translate([-20,0,-200])
{
	ring();
}
translate([20,0,-200])
{
	ring();
}
translate([40,0,-200])
{
	ring();
}
translate([-40,0,-200])
{
	ring();
}
translate([0,-40,-200])
{
	ring();
}
translate([0,40,-200])
{
	ring();
}
}
color("indigo")
{
translate([0,0,-195])
{
	ring();
}

}

for (i = [0:5]) {
			color("aqua")
			{ 
			translate([sin(360*i/6)*48, cos(360*i/6)*80, -200 ])
				ring();
				
}
}

for (i = [0:5]) {
			color("snow")
			{ 
			translate([sin(360*i/6)*128, cos(360*i/6)*120, -200 ])
				ring();
				
}
}
for (i = [0:5]) {
			color("blue")
			{ 
			translate([sin(360*i/6)*88, cos(360*i/6)*120, -200 ])
				ring();
				
}
}
for (i = [0:5]) {
			color("indigo")
			{ 
			translate([cos(360*i/6)*80, sin(360*i/6)*90, -200 ])
				ring();
				
}
}





