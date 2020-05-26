# Application Crashes

If your application crashes on iOS, try launching it using the simulator in Xcode. If there is code which is triggering the crash, the application will terminate showing an exception in the Xcode debugger with the thread highlighted in red with a reason for the crash.

Look for an error message similar to `Exception	NSException *	"Unhandled JS Exception: TypeError: undefined is not an object [...deleted]` which should help determine the JavaScript code causing the problem in the application.

Errors that manifest as a red screen error in development typically give rise to the application crashing in production if not handled correctly.
