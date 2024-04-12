- *mythrill : copy the given command and paste it on ubuntu terminal for solidity security of smart contracts:*
:_⏬
```
sudo apt update
```
# Install solc
```
sudo apt install software-properties-common
sudo add-apt-repository ppa:ethereum/ethereum
sudo apt install solc
```
***1.option***

```

# Install libssl-dev, python3-dev, and python3-pip
```
sudo apt install libssl-dev python3-dev python3-pip
```
# Install mythril
```
pip3 install mythril
myth version
```

***2. option***

**via Dokcer:**
*All Mythril releases, starting from v0.18.3, are published to DockerHub as Docker images under the mythril/myth name.*
*Docker CE:*

**Pull the latest release of mythril/myth**
```
$ docker pull mythril/myth
```


*Use docker run *mythril/myth* the same way you would use the myth command*
```
docker run mythril/myth --help
docker run mythril/myth disassemble -c "0x6060"

```

```
docker run -v $(pwd):/tmp mythril/myth analyze /tmp/contract.sol
```

```
contract Exceptions {

    uint256[8] myarray;
    uint counter = 0;
    function assert1() public pure {
        uint256 i = 1;
        assert(i == 0);
    }
    function counter_increase() public {
        counter+=1;
    }
    function assert5(uint input_x) public view{
        require(counter>2);
        assert(input_x > 10);
    }
    function assert2() public pure {
        uint256 i = 1;
        assert(i > 0);
    }

    function assert3(uint256 input) public pure {
        assert(input != 23);
    }

    function require_is_fine(uint256 input) public pure {
        require(input != 23);
    }

    function this_is_fine(uint256 input) public pure {
        if (input > 0) {
            uint256 i = 1/input;
        }
    }

    function this_is_find_2(uint256 index) public view {
        if (index < 8) {
            uint256 i = myarray[index];
        }
    }

}

```

***ALSO YOU CAN EXPLORE THIS FOR MORE SMART CONTRACTS➡️***
[auditing-smart-contracts)](https://hackenproof.com/blog/for-hackers/how-to-use-slither-for-auditing-smart-contracts)

**We can execute such a contract by directly using the following command:**

```
$ myth analyze <file_path>

```


***after that the final result wiil be like this:***


![image](https://github.com/Rjesh2006/Solidity_Smart_Contract_Analysis_Tools_and_Techniques/assets/143868643/b539693c-e1a2-4be9-9e7c-80f04d4a10ed)
