# Run Blockchain 

### MangoDB database
```sh
Drop Catapult Database
```

### createReplicatorsIPs.sh
```sh
cd cpp-xpx-chain/scripts/bootstrap
./createReplicatorsIPs.sh
```

### runCatapultServers.sh
```sh
cd cpp-xpx-chain/scripts/bootstrap
./runCatapultServers.sh
```

### Run API nodes
```sh
cd cpp-xpx-chain/_build         
./bin/sirius.bc data/api-node-0/
```

### Run 5 Peer nodes
```sh
cd cpp-xpx-chain/_build         
./bin/sirius.bc data/peer-node-0
./bin/sirius.bc data/peer-node-1
./bin/sirius.bc data/peer-node-2
./bin/sirius.bc data/peer-node-3
./bin/sirius.bc data/peer-node-4 
```
### Run script (After BC height reach >20)
```sh
cd go-xpx-chain-sdk
cd tools

./liquidity_provider/liquidity_provider -url=http://127.0.0.1:3000     -feeStrategy=middle     -sender=7AA907C3D80B3815BE4B4E1470DEEE8BB83BFEB330B9A82197603D09BA947230     -mosaic=storage     -initial=100000     -deposit=1000000     -slashingPeriod=500     -ws=5     -a=500     -b=500     -slashingAcc=0000000000000000000000000000000000000000000000000000000000000000     create

./liquidity_provider/liquidity_provider -url=http://127.0.0.1:3000     -feeStrategy=middle     -sender=7AA907C3D80B3815BE4B4E1470DEEE8BB83BFEB330B9A82197603D09BA947230     -mosaic=streaming     -initial=100000     -deposit=1000000     -slashingPeriod=500     -ws=5     -a=500     -b=500     -slashingAcc=0000000000000000000000000000000000000000000000000000000000000000     create

./liquidity_provider/liquidity_provider -url=http://127.0.0.1:3000     -feeStrategy=middle     -sender=7AA907C3D80B3815BE4B4E1470DEEE8BB83BFEB330B9A82197603D09BA947230     -mosaic=sc     -initial=100000     -deposit=1000000     -slashingPeriod=500     -ws=5     -a=500     -b=500     -slashingAcc=0000000000000000000000000000000000000000000000000000000000000000     create

./transfer/transfer -url=http://127.0.0.1:3000 \
 -feeStrategy=middle \
 -sender=819F72066B17FFD71B8B4142C5AEAE4B997B0882ABDF2C263B02869382BD93A0 \
 -receiver=E8D4B7BEB2A531ECA8CC7FD93F79A4C828C24BE33F99CF7C5609FF5CE14605F4 \
 -mosaic=0DC67FBE1CAD29E3\
 -amount=10000000000000

./transfer/transfer -url=http://127.0.0.1:3000 \
 -feeStrategy=middle \
 -sender=819F72066B17FFD71B8B4142C5AEAE4B997B0882ABDF2C263B02869382BD93A0 \
 -receiver=7C756F2D5E9F21E7215851FC26C9F6819DB7992F0CDD22D822AFBE764404E976 \
 -mosaic=0DC67FBE1CAD29E3\
 -amount=10000000000000

 ./transfer/transfer -url=http://127.0.0.1:3000 \
 -feeStrategy=middle \
 -sender=819F72066B17FFD71B8B4142C5AEAE4B997B0882ABDF2C263B02869382BD93A0 \
 -receiver=0A0EAC0E56FE4C052B66D070434621E74793FBF1D6F45286897240681A668BB1 \
 -mosaic=0DC67FBE1CAD29E3\
 -amount=10000000000000

 ./transfer/transfer -url=http://127.0.0.1:3000 \
 -feeStrategy=middle \
 -sender=819F72066B17FFD71B8B4142C5AEAE4B997B0882ABDF2C263B02869382BD93A0 \
 -receiver=1AAD933111E340E74FE9A44C12CEB359744BC9F8A6630ECA7DEA8B5AECE5C1C5 \
 -mosaic=0DC67FBE1CAD29E3\
 -amount=10000000000000

 ./transfer/transfer -url=http://127.0.0.1:3000 \
 -feeStrategy=middle \
 -sender=819F72066B17FFD71B8B4142C5AEAE4B997B0882ABDF2C263B02869382BD93A0 \
 -receiver=71FA42E336DE2DD74CE864A7A5A747C23EAB41BC6235CBA4C28E96B1900565FC \
 -mosaic=0DC67FBE1CAD29E3\
 -amount=10000000000000
 
./replicator_onboarding/replicator_onboarding -url=http://127.0.0.1:3000 -feeStrategy=middle -capacity=2048 -privateKey=2F985E4EC55D60C957C973BD1BEE2C0B3BA313A841D3EE4C74810805E6936053

./replicator_onboarding/replicator_onboarding -url=http://127.0.0.1:3000 -feeStrategy=middle -capacity=2048 -privateKey=415ABF3AA04493587AD0B3C6B594F369F74F4055CFBD2BF028AE29EA3C1C6BD3

./replicator_onboarding/replicator_onboarding -url=http://127.0.0.1:3000 -feeStrategy=middle -capacity=2048 -privateKey=48AD5278466BC0D765299AFD1A43D7EA7C3463A8078A54ACCD505D0FACA6B62F

./replicator_onboarding/replicator_onboarding -url=http://127.0.0.1:3000 -feeStrategy=middle -capacity=2048 -privateKey=7BF479B4D79F5752E6BCCE859D2D4731D898A9B16E90E6D479DF13CE15B8CD42

./replicator_onboarding/replicator_onboarding -url=http://127.0.0.1:3000 -feeStrategy=middle -capacity=2048 -privateKey=FB83889FB84E6D0596C046C27A1A151395666AF79AFB72DBF5B15161040F05E1
```

For checking transactions: http://localhost:3000/transactions/confirmed?pageNumber=4
- refer to the type thru cpp-xpx-chain/resources/supported-entities.json

For checking BC height: http://127.0.0.1:3000/chain/height
