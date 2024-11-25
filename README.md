# The students are expected to complete step 1 and 2 off session. From, step 3-11 we will learn in Session1 along with some theory of designing the testcases#

Enable the extension for Hardhat in Visual Studio Code: https://marketplace.visualstudio.com/items?itemName=NomicFoundation.hardhat-solidity

1. Install Docker for Desktop
2. Enable the Visual studio extension "Remote Explorer" from Microsoft

The "hardhat" directory has a dockerfile. In the terminal navigate to the "hardhat" directory.

3. Build the docker file: "docker build -f Dockerfile . -t hardhatimage". If the command fails, kindly search for the command suitable for your system architetcure. For eg: In mac os with M1 chip and Ventura OS, "docker build --platform linux/x86_64 -p 3000:3000 -t hardhatimage" will work.

4. Run the image: "docker run -d -i -v "Absolute path to hardhat folder":/hardhat -p 3000:3000 -t hardhatimage". (For above eaxmple "docker run -d -i -v "Absolute path to hardhat folder":/hardhat --platform linux/x86_64 -p 3000:3000 -t hardhatimage" will work. [Eg: The following command works at my end "docker run -d -i -v /Users/divyarathore/Documents/HederaDemo/hardhat:/hardhat --platform linux/x86_64 -p 3000:3000 -t hardhatimage"])

5. Search for the container "hardhatimage" in Remote Explorer. Open the container by clicking on folder button. A new window of VSCode will open with hardhat directory on your system with installed Node.js. If the navigation explorer does not open at hardhat, go to file -> open -> search where is hardhat (It should be located at / ). Open the terminal at "hardhat" in hardhatimage container.

6. Run the command "npm init -y". This command will generate package.json along with some other files. Edit package.json to add "hardhat": "hardhat" and remove "test" at key scripts. Also add a new key <"dependencies":{"hardhat":"^2.22.16"}> after key scripts. Now we are ready to install hardhat.

7. Run the command "npm cache clean --force".

8. Run the command "npm install hardhat". This will generate the node_modules folder with required dependencies.

9. Verify the hardhat installation: "ls node_modules/.bin/". This will have a folder named hardhat.

10. Run "npx hardhat". Press "enter" for all the questions asked. This should generate a contracts, test and ignition folder. This will take some time for installation.

11. Run the command "npx hardhat test test/Lock.js". This command will compile, run the contract Lock.js and will test the available Lock.sol contract.
