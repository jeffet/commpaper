

### Prerequisites  

* Charged laptop
* Browser (Chrome or Firefox)
* VM Link  (Contact the session coordinator to receive the linka and password)

### Accessing the environment
Log into the VM via the link provided 
http://<ip_address>/vnc.html

![Image of Yaktocat](images/VMLogin.png){:height="200px"}
Click connect and enter the provided password.

Open the terminal and change to HOME directory.
![Start terminal](images/startTerminal.png)

Delete and clone fabric-smaples:
![Git clone](images/cleanAndGitClone.png)

```
rm -rf fabric-samples
git clone https://github.com/hyperledger/fabric-samples.git
cd fabric-samples
```


[>> Next](README.md#setup)