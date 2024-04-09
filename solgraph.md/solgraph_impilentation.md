Update your package index:
```
sudo apt update
```

Install prerequisites:

```
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```

Add Docker’s official GPG key:


```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```


Set up the Docker repository:

```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

Update the package index again:

```
sudo apt update

```

Install Docker:
```
sudo apt install docker-ce
```

Check Docker version:
```
docker --version
```

(Optional) Add your user to the docker group: This allows you to run Docker commands without sudo, which can be more convenient.
```
sudo usermod -aG docker ${USER}
```


***Now we can start to install Solgraph:***

To simplify its use, we will use a Docker image (devopstestlab/solgraph) that I built.

```
docker pull devopstestlab/solgraph
```

*then creat the mycontcract.sol file to put ur smart contract code in ur ,mycontract.sol file*
``
vim mycontract.sol
```
*then put this or any smart code which u like to insert*

```sol
contract MyContract {
  uint balance;

  function MyContract() {
    Mint(1000000);
  }

  function Mint(uint amount) internal {
    balance = amount;
  }

  function Withdraw() {
    msg.sender.send(balance);
  }

  function GetBalance() constant returns(uint) {
    return balance;
  }
}
```

**Now, let’s run **solgraph**:*

```
docker run -it --rm -v $PWD:/data devopstestlab/solgraph

```

*The output lists the smart contracts found:*
**mycontract.sol**



*This image parse the current folder ($PWD) to convert each contract (*.sol files). It produces images by adding the .png extension to the contract.*

*For example, in our example, it produces an image*

**MyContract.sol.png:**

![image](https://github.com/Rjesh2006/slither_impli/assets/143868643/7384e38c-ea74-4e76-9304-1685c8dbbbfc)


