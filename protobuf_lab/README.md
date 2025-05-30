# installing the toolchain

## protoscope
````
go install github.com/protocolbuffers/protoscope/cmd/protoscope...@latest
````

then it's in /go/bin in your codespace instance

## protoc compiler

````
wget https://github.com/protocolbuffers/protobuf/releases/download/v25.8/protoc-25.8-linux-x86_64.zip
mkdir protoc
mv protoc-25.8-linux-x86_64.zip protoc
cd protoc/
unzip protoc-25.8-linux-x86_64.zip -d .
export PATH="$PATH:/workspaces/antoine-eulisa/protoc/bin"
````

# using

## encoding test data as protob
````
cat test-data.txt | protoc --encode=tutorial.Greet ./test.proto > test-data.protob
````

## getting raw data from EVS

it starts by getting the hexa values from EVS UI like so ![EVS screen](evs_get_raw.png)
then a tool must be used to convert the hexa back to its original binary value


## decoding by protoscope
````
/go/bin/protoscope test-data.protob 
/go/bin/protoscope /workspaces/antoine-eulisa/message-etias.dat 
````
