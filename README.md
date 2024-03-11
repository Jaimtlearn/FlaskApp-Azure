# FlaskApp-Azure
Basic Flask application over azure public network

# Pre-requisits
1. Check for the inbound rules of networking setting of VM machiene that it listens to the particular port, in my case it is 5001
2. install particular things:
<pre>sudo apt update && sudo apt install python3</pre>
then,
<pre>sudo apt install python3-pip</pre>
After installing pip manager, install dependencies by
<br>
<pre>pip install -r requirements.txt</pre>

3. Run command on terminal:
<pre>gunicorn --config gunicorn.conf app:app</pre>

4. copy public ip assigned to the Vm, copy it in the url bar, replace https with http, append this in the end, :(port provided by you), it should look like this, http://ip:port

# For Availabilty
for avalabilty of the app, I have created service of the app so even when shell is terminated it will not shutdown the process.
<br>
Command:
<pre>nohup gunicorn --config gunicorn.conf app:app > nohup.out 2>&1 & disown</pre>
