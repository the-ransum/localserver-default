# localserver-default
Just a default setup for a localized server for quickly testing webpages.

## [Requirements](#)
- Python 3.X or 2.X, for setup follow: [Installing Python](#installing-python)

## [Running a Local HTTP Server](#)
- Open your command prompt (Windows)/ terminal (macOS/ Linux).
- Navigate to the directory that your example is inside, using the `cd` command.
```shell
# include the directory name to enter it, for example -
cd Desktop/localserver-default/test
# use two dots to jump up one directory level if you need to
cd ..
```
- Enter the command to start up the server in that directory.
```shell
# If Python version returned above is 3.X
python3 -m http.server
# On windows try "python" instead of "python3", or "py -3"
# If Python version returned above is 2.X
python -m SimpleHTTPServer
```
- To view in your browser, navigate to [locahost:8000](http://locahost:8000/). 
- _By default, this will run the contents of the directory on a local web server, on port 8000. You can go to this server by going to the URL localhost:8000 in your web browser, if the working directory contains an `index.html` it will automatically use that as your main webpage, unless the direct path is selected to another `<some-filename>.html`, though if their is no `index.html` file, then you'll see the contents of the directory listed._
- For allowing webpage reload on-changes, follow [Reload on Saved Changes](#reload-on-saved-changes) to setup or use the example in [test/autoreload](test/autoreload)

## [Reload on Saved Changes](#)
For those who want your page to auto-reload when changes are made to itself, then [live.js](http://livejs.com/) is the goto. 
Just add the following to your `<head>`:
```html
<script type="text/javascript" src="https://livejs.com/live.js"></script>
```

The Advantages and Disadvantages of using this - 
__Advantages__:
- Easy setup
- Works seamlessly with popular browsers e.g. Firefox, Chrome, Safari, Opera, IE6+, etc.
- Only refreshes when you save changes.
- Removes the need for browser plugins or unwanted intervals, especially for debugging reasons.

__Disadvantages__:
- Does not work with file protocols: `file:///C:/Users/<username>/gits/livejs/live.html`.
- Server required.
- Must be removed when deploying: staging/prod
- Does not serve CDN.

### [Installing Python](#)
1. Go to [python.org](https://www.python.org/)
2. Under the Download section, click the link for Python "3.xxx".
3. At the bottom of the page, choose the Windows x86 executable installer and download it.
4. When it has downloaded, run it.
5. On the first installer page, make sure you check the "Add Python 3.xxx to PATH" checkbox.
6. Click Install, then click Close when the installation has finished.
7. Verify installation by opening a prompt and typing: `python -V`.

## [Known Problems](#)
- __They feature asynchronous requests__. Some browsers (including Chrome) will not run async requests (see [Fetching data from the server](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Fetching_data)) if you just run the example from a local file. This is because of security restrictions (for more on web security, read [Website security](https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps/Website_security)).
- __They feature a server-side language__. Server-side languages (such as PHP or Python) require a special server to interpret the code and deliver the results.
