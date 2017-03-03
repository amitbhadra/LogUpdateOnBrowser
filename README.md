This updates to the browser on localhost:5000 whenever there is any change in a local file result.

We do tail -f filename.txt > result & so that whatever log files are stored in filename.txt are pushed to this result file due to the tail command.

Just run the app: python app.py

We implement this using web sockets in Flask. We monitor the filename.txt using a library pyinotify. We wait for an event where the file is written. Once it is written, we flush the output on the page. No refreshing is required for this as this is a async process.
