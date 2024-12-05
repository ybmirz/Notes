## Having student information from the Database -
- Basically the student logs in and keep that information within the app, for the usual authentication period of Microsoft authentication
- Uses the supplied information to create a personalised **dashboard** for student activity, that states their upcoming classes today.
	- This means that it parses the timetable data from the [[Scientia Webserver Connection]] calendar app that Nottingham currently uses

## App Contains:
- It shall have a **moodle connection page parser** that allows users to view their specific moodle section. 
	- Check if you're able to modify and connect to the moodle API; more here [[Moodle Analysis]]
- It shall also have a **timetabling parser** that connects to the [[Scientia Webserver Connection]]
- It shall have a **whereismybus** schedule that shows the current bus timings that are upcoming throughout the day. [[Whereismybuss App Connection]]
- Of course, it should incorporate apps.nottingham [[Joget Workflow Investigation]] for easier access that other students can use 
	- This can just be a temporary thing for the 

- I'd like to be able to open PDF and lecture slides without downloading them (and clutter the phone storage) // I doubt it to be possible but directly caching it somehow and using the PDF cached for the time being and open it.
	- This means that the app should be able to read and open PDFs (user disabled)