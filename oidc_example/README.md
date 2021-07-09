# Simple RP and OP examples

These 2 examples can run on the same machine together following these steps.

Both servers "use" up a port, and running them on the same machine means they
need their own ports.  `simple_rp` supports providing a response url with a port
in it, so that will run on a random port (8000 in the example below) and
`simple_op` runs on port 443 - the standard https port.

Run the following:
1. Install python 3.6 `sudo apt install python3.6-dev`
2. In the project home directory, create a virtualenv `virtualenv -p python3.6 .`
3. Activate the virtualenv `source bin/activate`
4. Install oic from source using `python setup.py install`
5. In the `oidc_example/simple_op` directory install `requirements.txt` using `pip install -r requirements.txt`
6. In the `oidc_example/simple_rp` directory install `requirements.txt` using `pip install -r requirements.txt`
7. In the `oidc_example/simple_op` Start the op server on port 443 in using `sudo ../../bin/python3.6 src/run.py settings.yaml.example -p 443`
8. Another terminal, In the `oidc_example/simple_rp` directory, Start the rp server on port 8000 in `simple_rp` using `sudo ../../bin/python3.6 src/rp.py settings.yaml.example -p 8000`
9. Open the rp server in a browser, <https://localhost:8000/>
10. Enter the uid `localhost` to connect to the simple op server
11. Login using the credentials in `username: diana` and `password: krall`
12. Observe the user info is loaded by the RP server

