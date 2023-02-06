# API Usage
- API usage through it's [website](https://whereismybus.nottingham.edu.my), is quite **simple** lol, it seems that they just request the schedule per query:
	- http://whereismybus.nottingham.edu.my/mobile/www/api/get_schedule_new.php?q= // query per routing
	- Routing is defined here:
	- ![[Pasted image 20221009204737.png]]
	- With the index form **0 to 15** (In the order stated above)
- The data is standardised in a **json tree format** with the days stated in their **short form** and **value being plaintext** proven thruogh `No Bus M`
- Each child in the `timetable` parent is a *row record* in the front end

# Could be worked on?
- From this we can design the nott-a-student app to simply be requesting that same API and just parse the json output into something more useful and nicer
- **Mainly the Front-end design** for this part of the app, with some animation and colour design it'll look lovely.

