## Introduction

Hello world, this is MengZe, the developer of OpenRevise.

I am more than excited to announce the fresh start of this great community-based project, which is an integrated learning playground, with notes sharing as the main feature, Q&A panel, variety of learning tools (addons), as well as full customization options.

The concept of OpenRevise was inspired by the remarkable concept of Opensource, where everything will be transparent to users (excluding personal data which will be strongly protected) and people will have the opportunity to work upon it and create more interesting contents based on the existing project.

## Project Structure

The project is separated into two interconnected segments:

    OpenRevise API and OpenRevise WorkStation

### OpenRevise API

For the OpenRevise API, which is the backend of this project, it handles all the HTTP requests and act as the central database manager and user center. The registered users will be able to manage their accounts, contribute to the note database, as well as develop and test their own "addons" (which will be discussed later). 

Beside database, there will be customization panel and plenty of settings for users to customize their own workstation based on their preference, and everything can be done in the User Center.

#### API Features

- Database (user & data)
	- User records
		- credentials (username, password, email)
		- general info (no. hours, views, histories)
		- notes & addons authorship
		- settings control
	- Resources management
		- notes entries
		- addons configs
- HTTP Request handling
- Blog management
	- Blog database
	- Blog edit & update
- User management
	- Login & Signup
	- User profile
	- Leader board

### OpenRevise WorkStation

For the OpenRevise WorkStation, more interesting things will be happening as it will be fully customizable and each user can have his/her own workstation with different page layout, extensions and contents. It acts as the frontend of the project and it will handles the user interaction and the establishment of connection with the API.