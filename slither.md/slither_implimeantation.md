
*install Slither
Begin with installing solc – Solidity compiler:*

```
sudo apt install software-properties-common
```
```
sudo add-apt-repository ppa:ethereum/ethereum
```
```
sudo apt install solc
```

*You should also install the solc-select. It is used for quick installation and switching between Solidity compiler versions.*

Simply run 
```
pip3 install solc-select
```

*After the solc and solc-select are installed with no errors, we can proceed to the Slither installation. It can be done in three ways:*

Using Pip:
``
pip3 install slither-analyzer
``
**check a smart contract using Slither**

*After you defined a contract that you want to check, the easiest way is just to run slither [target]. The target can be specified in several ways:*

**Example: slither SecureContract.sol**

*now put your smart contracts to check the threats and error in in ur smart contract*
*use this smart contrats to checks threats and error also u can use any code which u like to check :-*


```
pragma solidity ^0.4.15;

contract Missing{
    address private owner;

    modifier onlyowner {
        require(msg.sender==owner);
        _;
    }

    // The name of the constructor should be Missing
    // Anyone can call the IamMissing once the contract is deployed
    function IamMissing()
        public 
    {
        owner = msg.sender;
    }

    function withdraw() 
        public 
        onlyowner
    {
       owner.transfer(this.balance);
    }
}
```

*The easiest way to scan the local copy of a smart contract is to run slither with a contract name. Within seconds you will receive the results:*

```
slither mycontract.sol
```
*Now' u will be able to see the whats the threats and error ur smart constract contain (**error  will be in greeen colors**)*

**final interface**

**interface:--**

![image](https://github.com/Rjesh2006/slither_impli/assets/143868643/6cbc9709-4075-4efa-8bd2-056148ba80ea)

