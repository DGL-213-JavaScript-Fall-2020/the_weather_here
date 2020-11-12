# The Weather Here
This is a slightly modified version of the project code developed by [The Coding Train](https://thecodingtrain.com/) as part of their video series [Working with Data and APIs in JavaScript](https://www.youtube.com/playlist?list=PLRqwX-V7Uu6YxDKpFzf_2D84p0cyk4T7X).

**Note** that for this application to work you must have an [OpenWeatherMap API](https://openweathermap.org/api) API Key. Direction to obtain this follow.

## Obtain an OpenWeatherMap API key
The following steps walk you through the process of generating a new OpenWeatherMap API key. It's pretty straightforward though - you might not need the instructions, other than to tell you where to look for the API key generator. Note that after creating your account a new API 'default' key is automatically created for you, but it is good practice to use appropriately named API keys, so that they are easier to track.

Note as well that it may take some hours before the newly generated API key is usable, so if you try it right away and it doesn't work, don't panic - just give it two or three hours then try again.
1. Visit [OpenWeatherMap API](https://openweathermap.org/api)
2. Click the 'Sign In' link on the upper right, then choose 'Create an Account' on the login page.
3. Create and verify your account.
4. After verifying and logging into your account click on the dropdown menu on your username on the upper right hand corner of the page. Select 'My API Keys' from the menu.
5. Generate a new API key with the name 'the_weather_here' 

## Storing the API key and running the app
1. Clone this repository to your hard drive using GitHub Desktop
2. Open the resulting local repository with VS Code
3. Open the `.env-sample` file. Replace `'YOUR_API_KEY_HERE'` with your the_weather_here API key generated in the last section. **Do not** include any spaces or quotations in the `.env` file.
4. Rename `.env-sample` to `.env`.
5. Open a new Terminal window at the root directory of the repository and install npm packages using the `npm install` command at the command line
4. Run the server using the command line command: `node index.js` (the default port should be 3000, but if it's something different you should see it stated in the terminal window as the server starts)
5. Navigate to [127.0.0.1:3000](127.0.0.1:3000) to view the app

## A couple key notes:
* The [Dark Sky API](https://darksky.net/dev) has been replaced with [OpenWeatherMap API](https://openweathermap.org/api). Dark Sky was purchased by Apple recently, and the API has been shut down. Note that structure of the JSON object returned from OpenWeatherMap is different from Dark Sky; I have made as minimal changes as possible to ensure parity with the original code.
* It appears as though the second API in the app - the [Open AQ API](https://docs.openaq.org/) - may be failing as well. At least, it seems like it hasn't been maintained very regularly in recent years. If you follow the process presented in the video to spoof your location data in Chrome you'll likely still not find that there is any AQ data for most locations (in my tests Moscow worked, but few others). As such, you will likely encounter an console error relating to line 24 in `sketch.js`, which is expected behaviour. 
* Barring these two issues (a change in weather API, and AQ API not necessarily always providing data) the app *should* work fine. That said, if you do somehow end up with a corrupted `database.db` file (for example, if you have only partial entries in the database file for some reason), then your best bet is to delete the database file and restart the server.
* Finally, I suggest using the `node index.js` method of running the test server for this app, rather than trying to use Live Server. With that in mind, you may want to install nodemon (i.e. `node install -g nodemon` in your terminal window) to get server live reloading, rather than terminating and reloading the server manually each time you make a change to `index.js` (this process is discussed in the video series).