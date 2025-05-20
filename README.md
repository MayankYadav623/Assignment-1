Installation of IPFS on local machine. Further, uploading the files (such as photos, audio, and video) on IPFS .
IPFS: What You Need to Know

What is IPFS?

The InterPlanetary File System (IPFS) is a decentralized and distributed file storage system that seeks to connect all computing devices with the same system of files. It stands out from traditional file storage methods due to its unique way of storing and accessing files, directories, websites, and data. It’s a popular type of web3 storage that uses peer-to-peer (P2P) technology, making it akin to a single BitTorrent swarm for exchanging objects within one Git repository.

How is content organized on IPFS?

How It’s Stored:

In IPFS, files and other data are stored in a network of nodes. These nodes are essentially computers participating in the IPFS network, each storing only a portion of the entire data. When a file is added to IPFS, it is split into ### smaller blocks, hashed, and given a unique fingerprint called a cryptographic hash.

How It’s Retrieved:

To retrieve data, a user requests it using the hash. IPFS locates the nodes storing the corresponding blocks and downloads them. This decentralized approach means that content can be served faster and more reliably, as it does not rely on a single point of failure.

Understanding Location Addressing vs Content Addressing:

Traditional web uses location-based addressing, where content is accessed by its location on a server (URL). IPFS uses content-based addressing, where content is accessed by a hash of its content. This ensures that as long as the content remains the same, its address does not change, regardless of where it’s stored.



Installation of IPFS

Commands (IPFS)
1.	Install the IPFS through WSL: wget https://dist.ipfs.tech/kubo/v0.32.1/kubo_v0.32.1_linux-amd64.tar.gz 
Or 
wget https://github.com/ipfs/kubo/releases/download/v0.32.1/kubo_v0.32.1_linux-amd64.tar.gz
2.	tar -xvzf kubo_v0.32.1_linux-amd64.tar.gz
3.	Kubo is a reference implementation of IPFS in Go: cd kubo 
4.	ls
5.	sudo bash install.sh
6.	ipfs –version
7.	ipfs init
8.	ipfs daemon
9.	On Browser: http://127.0.0.1:5001/webui
10.	To run ipfs daemon in background: ipfs daemon > ipfs.log 2>&1 &
11.	This is daemon ID: [1] 772
12.	Add file: echo "Hello, IPFS!" > hello.txt
13.	ipfs add hello.txt
14.	ipfs cat <CID>
15.	Add a directory: 
mkdir myfolder
echo "File 1 content" > myfolder/file1.txt
echo "File 2 content" > myfolder/file2.txt
16.	ipfs add -r myfolder
17.	ps aux | grep ipfs
18.	kill <PID>
19.	in Browser you can directly run this to see the IPFS: https://ipfs.io/ipfs/QmWd9cavD8UGZQcqYBVhZqs2Jure5W9cgxR7S6TC4StfZe

20.	Assignment 5: 
Perform encryption and privacy on IPFS through command line.  
IPFS privacy and encryption
1.	echo "Hello, IPFS!" > myfile.txt
2.	ipfs add myfile.txt
3.	openssl enc -aes-256-cbc -pbkdf2 -iter 100000 -salt -in myfile.txt -out myfile_encrypted.txt -pass pass:yourpassword
4.	ipfs add myfile_encrypted.txt
5.	cat myfile_encrypted.txt
6.	openssl enc -d -aes-256-cbc -pbkdf2 -iter 100000 -in myfile_encrypted.txt -out decrypted_file.txt -pass pass:yourpassword
7.	cat decrypted_file.txt
8.	ipfs add decrypted_file.txt
