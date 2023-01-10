<!DOCTYPE html>
<html lang="en">
<head>
	<!-- web page title -->
	<title>Course Sshedule</title>
	<!-- declare character encoding -->
	<meta charset="utf-8">
	<!-- author of the document -->
	<meta name="author" content="Larry Pfaff">
	<!-- Keywords and Description for Search Engines -->
	<meta name="description" content="brief page description">
	<meta name="keywords" content="HTML, CSS, javaScript">
	<!-- Viewport Configuration for Mobile Devices Example -->
	<!-- <meta name="viewport" content="width=device-width, initial-scale=1.0"> -->
	<!-- stylesheet link -->
	<link rel="stylesheet" href="../css/cgs1821.css">

	<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.5.1/jquery.min.js" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.29.1/moment.min.js" crossorigin="anonymous"></script>

	<script type="text/javascript">
		$(document).ready(function (){
			function formatDate(date) {
				var monthNames = [
				"Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"
				];
				
				var dayNames = [
				"Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"
				];
				
				var dayIndex = date.getDay();
				var dt = date.getDate();
				var monthIndex = date.getMonth();
				var year = date.getFullYear();

			  return dayNames[dayIndex] + ', '+ monthNames[monthIndex] + ' ' +dt + ', ' + year;
			}

			//January = 0.
			//December = 11.
			const d = new Date(2023,0,9);
			const today = new Date();
			//alert(d);
			var csd = formatDate(new Date(d)); 
			
			//alert(csd);
			$("div#coursestart").append("Course Start Date: " + csd); //,"ddd, mmmm dS, yyyy"));
			
			var m = Math.floor(d.getMonth());
			var term, t;
			switch (m)
			{
				case 0:
				case 1:
				case 2: 
				
				  term = "Spring";
				  t = "W"
				   break;
				case 3: 
				case 4:
				case 5:
				case 6: 
			
				  term = "Summer";
				  t = "S"
				   break;
				case 7: 
				case 8:
				case 9:
				case 10: 
				case 11:
				
				  term = "Fall";
				  t = "F"
				   break;		
				default: 
				   "none";
			}
			
			var getTwodigitYear = d.getFullYear().toString().substring(2); // get last two digits from year
			//$("#coursename").append("CGS1820 " + season[arr] + " " + Math.floor(d.getYear()+1900) );
			$("#coursename").append(t + getTwodigitYear + " CGS1821");
			
			const daysFromStart =[6,6,6,13,20,27,34,34,41,48,55,62,69,76,83,90,97,104,108,111];
			const assignments = ["Welcome Discussion",
								"Module 1 Inroduction",
								"Syllabus Agreement",
								"Module 2 Shape up!",
								"Module 3 Shape up!",
								"Module 4 Shape up!",
								"Exam 1",
								"Module 5 Shape up!",
								"Module 6 Shape Up!",
								"Module 7 Shape up!",
								"Final Project Create Form Page",
								"Exam 2",
								"Module 8 Lab Quiz",
								"Module 9 Shape up!",
								"Module 10 Shape up!",
								"Final Project Create Home Page",
								"Exam 3",
								"Final Project",
								"Final Project Reviews",
								"Post Grades in Canvas"];
			const chapters = ["",
								"Chapter 2",
								"",
								"Chapter 8",
								"Chapter 9",
								"Chapter 10",
								"Chapter 8,9,10",
								"Chapter 11",
								"Chapter 12",
								"Chapter 13",
								"",
								"Chapter 11,12,13",
								"Chapter 16",
								"Chapter 14",
								"Chapter 15",
								"",
								"Chapter 14,15,16",
								"",
								"",
								""
								];
			
			
			for (let i = 0; i <= daysFromStart.length; i++) {
				//alert(daysFromStart[i]);
				var nd = new Date(d);
				var ed = new Date(d);
				nd.setDate(nd.getDate()+daysFromStart[i]);
				
				$( "#a"+i ).append(assignments[i]);
				$( "#c"+i ).append(chapters[i]);
				$( "#d"+i ).append( nd.toDateString());
				if( nd < today ) {
					$( "#d"+i ).addClass("strike");
				} else {
					$( "#d"+i ).removeClass("strike");
				}
				
				if(assignments[i].includes("Exam") ) {
					$( "#h"+i ).addClass("g");
				} 
				if(assignments[i].includes("Final") ) {
					$( "#h"+i ).addClass("y");
				}	
				if(assignments[i].includes("Post") ) {
					$( "#h"+i ).addClass("b");
				}
			}
			
   });
</script>
<!-- Makes css life easier -->
<style>element {
}
  @media (prefers-color-scheme: dark)
body {
  --warning-color: #ffbd4f;
}
body {
  --warning-color: #ffa436;
}
  @media only screen and (max-width: 959px)
body {
  padding: 0 75px;
}
body {
  background-size: 64px 32px;
  background-repeat: repeat-x;
  padding: 0;
  min-width: 13em;
}
body {
  display: flex;
  flex-direction: column;
  box-sizing: border-box;
  min-height: 100vh;
  padding: 40px 48px;
  align-items: center;
  justify-content: center;
}
html|body {
  margin: 0;
}
:root:not(.system-font-size) {
  font-size: 15px;
}
:root {
  --in-content-container-min-width: 13em;
  --in-content-container-max-width: 52em;
}
  @media (max-width: 830px)
:root {
  --in-content-sidebar-width: 118px;
}
:root {
  font: message-box;
    font-size: ;
  color: var(--in-content-page-color);
}
  @media (prefers-color-scheme: dark)
:host, :root {
  --in-content-page-background: rgb(28,27,34);
  --in-content-page-color: rgb(251,251,254);
  --in-content-deemphasized-text: rgb(191,191,201);
  --in-content-box-background: rgb(35, 34, 43);
  --in-content-box-background-odd: rgba(249,249,250,0.05);
  --in-content-box-info-background: rgba(249,249,250,0.15);
  --in-content-border-color: rgba(249,249,250,0.2);
  --in-content-border-hover: rgba(249,249,250,0.3);
  --in-content-border-invalid: rgb(255,132,139);
  --in-content-error-text-color: #FF9AA2;
  --in-content-button-background: rgb(43,42,51);
  --in-content-button-background-hover: rgb(82,82,94);
  --in-content-button-background-active: rgb(91,91,102);
  --in-content-icon-color: rgb(251,251,254);
  --in-content-primary-button-text-color: rgb(43,42,51);
  --in-content-primary-button-background: rgb(0,221,255);
  --in-content-primary-button-background-hover: rgb(128,235,255);
  --in-content-primary-button-background-active: rgb(170,242,255);
  --in-content-danger-button-background: #ff848b;
  --in-content-danger-button-background-hover: #ffbdc5;
  --in-content-danger-button-background-active: #ffdfe7;
  --in-content-table-background: rgb(35, 34, 43);
  --card-outline-color: var(--grey-60);
  --dialog-warning-text-color: var(--red-40);
  scrollbar-color: rgba(249,249,250,.4) rgba(20,20,25,.3);
}
:host, :root {
  --in-content-page-color: rgb(21, 20, 26);
  --in-content-page-background: #fff;
  --in-content-text-color: var(--in-content-page-color);
  --in-content-deemphasized-text: rgb(91, 91, 102);
  --in-content-box-background: #fff;
  --in-content-box-background-odd: rgba(12, 12, 13, 0.05);
  --in-content-box-border-color: color-mix(in srgb, currentColor 41%, transparent);
  --in-content-box-info-background: #f0f0f4;
  --in-content-item-hover: color-mix(in srgb, var(--in-content-primary-button-background) 20%, transparent);
  --in-content-item-hover-text: var(--in-content-page-color);
  --in-content-item-selected: var(--in-content-primary-button-background);
  --in-content-item-selected-text: var(--in-content-primary-button-text-color);
  --in-content-icon-color: rgb(91,91,102);
  --in-content-accent-color: var(--in-content-primary-button-background);
  --in-content-accent-color-active: var(--in-content-primary-button-background-hover);
  --in-content-border-hover: var(--grey-90-a50);
  --in-content-border-invalid: var(--red-50);
  --in-content-border-color: #d7d7db;
  --in-content-error-text-color: #c50042;
  --in-content-link-color: var(--in-content-primary-button-background);
  --in-content-link-color-hover: var(--in-content-primary-button-background-hover);
  --in-content-link-color-active: var(--in-content-primary-button-background-active);
  --in-content-link-color-visited: var(--in-content-link-color);
  --in-content-button-text-color: var(--in-content-text-color);
  --in-content-button-text-color-hover: var(--in-content-text-color);
  --in-content-button-text-color-active: var(--in-content-button-text-color-hover);
  --in-content-button-background: rgba(207,207,216,.33);
  --in-content-button-background-hover: rgba(207,207,216,.66);
  --in-content-button-background-active: rgb(207,207,216);
  --in-content-button-border-color: transparent;
  --in-content-button-border-color-hover: transparent;
  --in-content-button-border-color-active: var(--in-content-button-border-color-hover);
  --in-content-primary-button-text-color: rgb(251,251,254);
  --in-content-primary-button-text-color-hover: var(--in-content-primary-button-text-color);
  --in-content-primary-button-text-color-active: var(--in-content-primary-button-text-color);
  --in-content-primary-button-background: #0061e0;
  --in-content-primary-button-background-hover: #0250bb;
  --in-content-primary-button-background-active: #053e94;
  --in-content-primary-button-border-color: transparent;
  --in-content-primary-button-border-hover: transparent;
  --in-content-primary-button-border-active: transparent;
  --in-content-danger-button-background: #e22850;
  --in-content-danger-button-background-hover: #c50042;
  --in-content-danger-button-background-active: #810220;
  --in-content-focus-outline-color: var(--in-content-primary-button-background);
  --in-content-focus-outline-width: 2px;
  --in-content-focus-outline-offset: 2px;
  --in-content-focus-outline-inset: calc(-1 * var(--in-content-focus-outline-width));
  --in-content-focus-outline: var(--in-content-focus-outline-width) solid var(--in-content-focus-outline-color);
  --in-content-table-background: #f8f8fa;
  --in-content-table-border-color: var(--in-content-box-border-color);
  --in-content-table-header-background: var(--in-content-primary-button-background);
  --in-content-table-header-color: var(--in-content-primary-button-text-color);
  --in-content-sidebar-width: 240px;
  --dialog-warning-text-color: var(--red-60);
  --checkbox-border-color: var(--in-content-box-border-color);
  --checkbox-unchecked-bgcolor: var(--in-content-button-background);
  --checkbox-unchecked-hover-bgcolor: var(--in-content-button-background-hover);
  --checkbox-unchecked-active-bgcolor: var(--in-content-button-background-active);
  --checkbox-checked-bgcolor: var(--in-content-primary-button-background);
  --checkbox-checked-color: var(--in-content-primary-button-text-color);
  --checkbox-checked-border-color: transparent;
  --checkbox-checked-hover-bgcolor: var(--in-content-primary-button-background-hover);
  --checkbox-checked-active-bgcolor: var(--in-content-primary-button-background-active);
  --blue-40: #45a1ff;
  --blue-50: #0a84ff;
  --blue-60: #0060df;
  --grey-30: #d7d7db;
  --grey-60: #4a4a4f;
  --grey-90-a10: rgba(12, 12, 13, 0.1);
  --grey-90-a20: rgba(12, 12, 13, 0.2);
  --grey-90-a30: rgba(12, 12, 13, 0.3);
  --grey-90-a50: rgba(12, 12, 13, 0.5);
  --grey-90-a60: rgba(12, 12, 13, 0.6);
  --green-50: #30e60b;
  --green-60: #12bc00;
  --green-70: #058b00;
  --green-80: #006504;
  --green-90: #003706;
  --orange-50: #ff9400;
  --red-40: #ff4f5e;
  --red-50: #ff0039;
  --red-60: #d70022;
  --red-70: #a4000f;
  --red-80: #5a0002;
  --red-90: #3e0200;
  --yellow-50: #ffe900;
  --yellow-60: #d7b600;
  --yellow-60-a30: rgba(215, 182, 0, 0.3);
  --yellow-70: #a47f00;
  --yellow-80: #715100;
  --yellow-90: #3e2800;
  --shadow-10: 0 1px 4px var(--grey-90-a10);
  --shadow-30: 0 4px 16px var(--grey-90-a10);
  --card-padding: 16px;
  --card-shadow: var(--shadow-10);
  --card-outline-color: var(--grey-30);
  --card-shadow-hover: var(--card-shadow), 0 0 0 5px var(--card-outline-color);
  accent-color: var(--in-content-accent-color);
  color-scheme: light dark;
}</style>
</head>

<body>
	<header>
		<h1 id="coursename"></h1>
	</header>
	<main>
	<h3><div  id="coursestart"></div></h3>
        
		<div class="inner">
	
		<table id="schedule">
			<caption>List of assignments and due dates as noted on the Canvas calendar</caption>
			<thead>
			<tr>
			<th>&#10004;</th><th>Textbook Readings</th><th>Assignment</th><th>Due Date</th>
			</tr>
			</thead>
			<tbody>
			<tr  id="h0">
			<td><input class="ckbox" type="checkbox" /></td><td><div id="c0"></div></td><td><div id="a0"></div></td><td><div id="d0"></div></td>
			</tr>
			<tr  id="h1">
			<td><input class="ckbox"  type="checkbox" /></td><td><div id="c1"></div></td><td><div id="a1"></div></td><td><div id="d1"></div></td>
			</tr>
			<tr  id="h2">
			<td><input class="ckbox"  type="checkbox" /></td><td ><div id="c2"></div></td><td><div id="a2"></div></td><td><div id="d2"></div></td>
			</tr>
			<tr  id="h3">
			<td><input class="ckbox"  type="checkbox" /></td><td><div id="c3"></div></td>  <td><div id="a3"></div></td><td><div id="d3"></div></td>
			</tr>
			<tr  id="h4">
			<td><input class="ckbox"  type="checkbox" /></td><td><div id="c4"></div></td><td><div id="a4"></div></td><td><div id="d4"></div></td>
			</tr>
			<tr  id="h5">
			<td><input class="ckbox"  type="checkbox" /></td><td  ><div id="c5"></div></td><td><div id="a5"></div></td><td><div id="d5"></div></td>
			</tr>
			<tr  id="h6">
			<td><input class="ckbox"  type="checkbox" /></td> <td><div id="c6"></div></td> <td><div id="a6"></div></td><td><div id="d6"></div></td>
			</tr>
			<tr  id="h7">
			<td><input  class="ckbox" type="checkbox" /></td><td ><div id="c7"></div></td><td><div id="a7"></div></td><td><div id="d7"></div></td>
			</tr>
			<tr  id="h8">
			<td><input  class="ckbox" type="checkbox" /></td><td><div id="c8"></div></td> <td><div id="a8"></div></td><td><div id="d8"></div></td>
			</tr>
			<tr  id="h9">
			<td><input  class="ckbox" type="checkbox" /></td><td ><div id="c9"></div></td><td><div id="a9"></div></td><td><div id="d9"></div></td>
			</tr>
			<tr  id="h10">
			<td><input  class="ckbox" type="checkbox" /></td><td><div id="c10"></div></td><td><div id="a10"></div></td><td><div id="d10"></div></td>
			</tr>
			<tr  id="h11">
			<td><input  class="ckbox" type="checkbox" /></td><td ><div id="c11"></div></td><td><div id="a11"></div></td><td><div id="d11"></div></td>
			</tr>
			<tr  id="h12">
			<td><input  class="ckbox" type="checkbox" /></td> <td><div id="c12"></div></td> <td><div id="a12"></div></td><td><div id="d12"></div></td>
			</tr>
			<tr  id="h13">
			<td><input  class="ckbox" type="checkbox" /></td><td><div id="c13"></div></td><td><div id="a13"></div></td><td><div id="d13"></div></td>
			</tr>
			<tr  id="h14">
			<td><input  class="ckbox" type="checkbox" /></td><td><div id="c14"></div></td><td><div id="a14"></div></td><td><div id="d14"></div></td>
			</tr >
			<tr  id="h15">
			<td><input  class="ckbox" type="checkbox" /></td><td ><div id="c15"></div></td><td><div id="a15"></div></td><td><div id="d15"></div></td>
			</tr>
			<tr  id="h16">
			<td><input  class="ckbox" type="checkbox" /></td><td><div id="c16"></div></td><td><div id="a16"></div></td><td><div id="d16"></div></td>
			</tr>
			<tr  id="h17">
			<td><input  class="ckbox" type="checkbox" /></td><td><div id="c17"></div></td><td><div id="a17"></div></td><td><div id="d17"></div></td>
			</tr>
			<tr  id="h18">
			<td><input  class="ckbox" type="checkbox" /></td><td><div id="c18"></div></td><td><div id="a18"></div></td><td><div id="d18"></div></td>
			</tr>
			<tr  id="h19">
			<td><input  class="ckbox" type="checkbox" /></td><td><div id="c19"></div></td><td><div id="a19"></div></td><td><div id="d19"></div></td>
			</tr>				
			</tbody>
		</table>
		</div>	
		<p>&nbsp;</p>
	</main>
	
		
	 <footer id="footer" class="footer">
                        <div class="footer-container footer-sf-info">
                            <div class="span-4 footer-branding">
                                <a class="footer-branding-img" href="/" title="Visit Santa Fe College">
                                    <img src="https://www.sfcollege.edu/Assets/sf/master/img/sf-logo.svg" alt="" width="330"/>
                                    <address>
                                        <a title="Our address is 3000 NW 83rd Street, Gainesville, Florida 32606" href="https://www.google.com/maps/place/Santa+Fe+College/@29.680926,-82.433845,17z/data=!3m1!4b1!4m2!3m1!1s0x87185991074b1b63:0xf5f7cea054a78d01">3000 NW 83rd Street<br> Gainesville, FL 32606</a>
                                            <br>
                                                <a title="Call us at 352-395-5000 today" href="tel:3523955000">352-395-5000</a>
                                            </address>
                                        </div>
                                    </div>
                                </footer>
	
</body>
</html>
