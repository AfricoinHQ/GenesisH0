# GenesisH0
A python script for creating the parameters required for a unique genesis block. SHA256/scrypt/X11/X13/X15.

### Dependencies
    sudo pip install scrypt construct==2.5.2

    
### Examples
The Nonce has to be between

     0 and 4294967294
Create the original genesis hash found in Bitcoin

    python genesis.py -z "Jan 15 2021 Africoin was born." -n 12084524 -t 1610694000 -a scrypt -b 0x1e0ffff0
Output:

    coinbase:                                                                                                                    
    04ffff001d01043141667269636f696e2068617320626563616d652061207265616c69747920696e7374656164206f6620616e20696465612e           
    algorithm: scrypt                                                                                                            
    merkle hash: 81e292852b77a6b6e0bc3e02d39dd0132a9d6db36b216501db9daf2720f6e112                                                
    pszTimestamp: Africoin has became a reality instead of an idea.                                                              
    pubkey: 04678afdb0fe5548271967f1a67130b7105cd6a828e03909a67962e0ea1f61deb649f6bc3f4cef38c4f35504e51ec112de5c384df7ba0b8d578a4c702b6bf11d5f                                                                                                                
    time: 1610694000                                                                                                             
    bits: 0x1e0ffff0 
    genesis hash found!
    nonce: 2083236893
    genesis hash: 000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f
Create the regtest genesis hash found in Bitcoin

    python genesis.py -z "The Times 03/Jan/2009 Chancellor on brink of second bailout for banks" -n 2 -t 1296688602 -b 0x207fffff

Create the original genesis hash found in Litecoin

    python genesis.py -a scrypt -z "NY Times 05/Oct/2011 Steve Jobs, Apple’s Visionary, Dies at 56" -p "040184710fa689ad5023690c80f3a49c8f13f8d45b8c857fbcbc8bc4a8e4d3eb4b10f4d4604fa08dce601aaf0f470216fe1b51850b4acf21b179c45070ac7b03a9" -t 1317972665 -n 2084524493
    


### Options
    Usage: genesis.py [options]
    
    Options:
      -h, --help show this help message and exit
      -t TIME, --time=TIME  the (unix) time when the genesisblock is created
      -z TIMESTAMP, --timestamp=TIMESTAMP
         the pszTimestamp found in the coinbase of the genesisblock
      -n NONCE, --nonce=NONCE
         the first value of the nonce that will be incremented
         when searching the genesis hash
      -a ALGORITHM, --algorithm=ALGORITHM
         the PoW algorithm: [SHA256|scrypt|X11|X13|X15]
      -p PUBKEY, --pubkey=PUBKEY
         the pubkey found in the output script
      -v VALUE, --value=VALUE
         the value in coins for the output, full value (exp. in bitcoin 5000000000 - To get other coins value: Block Value * 100000000)
      -b BITS, --bits=BITS
         the target in compact representation, associated to a difficulty of 1

