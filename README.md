# Homework-18

Before starting we need to make sure that we have all our tools to create our network!

First we'll need to install these necessary tools. On these websites you can look through and install the Mycrypto and Go ethereum. THese will help us create our blockchain! follow the steps on each website to fuly and correctly install each tool

https://geth.ethereum.org/downloads/

https://download.mycrypto.com/

You remember that Go Ethereum tool you downloaded, now we are going to put it to use!
the puppeth tool is somethong that was bundled to Go Ethereum when you downloaded it.
you can go to terminal(mac) or gitbash(windows) for the next steps.
once in either of those you can type in the command ./puppeth, this should bring up a prompt.
Once thats there go ahead and type in a name for your network and hit enter. After that press 2 to pick the configure genesis option  and then hit 1 on the next option to choose createnew genesis from scratch.
 
 now you want to choose 1 to pick proof of authority and then youll be aske if you want to pre-fund an account.
 this is 100% up to you. If you choose to type in an ethereum address without the 0x prefix and hit enter to continue
 continue until you get to the chain Id prompt, come up with a number code you can remember and write it down for safe keeping! now for the next part.
 
 Now we need to export your genesis network into a json file. At the puppeth prompt navigate to manage existing genesis by inputing 2 and hitting enter, you might need to type in your netwrok name again(just to let em know the boss is back in town).
Then hit 2 to choos the export genesis configuration and continue with the default directory by hitting enter which will export several files to you. But all you need is the file with your network name followed by .json. you can now exit puppeth.

We now have to creat the node directory using the geth command, type in:
./geth account new --datadir node1
do the same for the second node but call it node2
now we initialize ech node by typing in:
./geth init yournetwrok.json --datadir node1
do the same for node 2. And now we are almost done!

Now its time to bring your block chain to life!
with the two nodes your created one will be mining and the other will be a connection that helps you connect with apps like MyCrypto.
now open your terminal agian and navigate to your designated network and type:
./geth --datadir node1 --mine --minerthreads 1, this will set the first node as a mining node
then copy the encode address after you press enter and run the code.
now type:
./geth --datadir node2 --port 30304 --rpc --botnodes "your encode address" --ipcdisable(if you are running on windows)

Now head over to your MyCrypto and find the private key to your pre-funded address and save it for later.
unlock your waller using the mnemonic phrase and then selesc the ETH you used that pre-funed the chain and on the dropdown list select wallet info.
change the network to custom id and then fill in the necessary elements and then go ahead and process it.
next go to the private key tab on the home page and unlock it. 
After this you should see a huge change in your wallet!

Now we can try go through a transaction ourselves. Copy the pre-funded address into the the address blank and enter a amount and then hit send transaction. Then click check tx status when you recieve the green message and when when your status says successful you know the transaction went through!!

Congrats! You have gone through and have created your first transaction on your blockchain!
![image](https://user-images.githubusercontent.com/71734654/113773695-f6618800-96eb-11eb-8ee9-0fa9c259ed85.png)

