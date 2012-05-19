Flipboard-like update checker
=============================

A Flipboard-like update checker.

1. Copy in your project classes `SMUpdateNotifier`, `SMURLConnection` and protocol `SMUpdaterDelegate`

2. Upload a file to a web server and set the value of REMOTE_VERSION_FILE<br/>
   File should contain just the version number, e.g. 1.2
3. Set the value of APP_NAME
4. Whenever you like to check for a new version just use this code.
   
	`SMUpdateNotifier *n = [[SMUpdateNotifier alloc] initWithDelegate:self];`<br/>
	`[n checkIfNewVersionExists];`

5. Your class should implement the `SMUpdaterDelegate`, which has three delegate methods

	`-(void) newVersionExists:(NSString *)versionNumber`<br/>
	`-(void) thereIsNoNewVersion`<br/>
	`-(void) requestFailedwithError:(NSError *) error`<br/>

Names should be pretty self-explanatory :)

Check out the code in the application delegate to see an example.