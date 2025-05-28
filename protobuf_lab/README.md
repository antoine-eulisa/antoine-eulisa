go install github.com/protocolbuffers/protoscope/cmd/protoscope...@latest
wget https://github.com/protocolbuffers/protobuf/releases/download/v25.8/protoc-25.8-linux-x86_64.zip
mkdir protoc
mv protoc-25.8-linux-x86_64.zip protoc
cd protoc/
unzip protoc-25.8-linux-x86_64.zip -d .
export PATH="$PATH:/workspaces/antoine-eulisa/protoc/bin"
cat test-data.txt | protoc --encode=tutorial.Greet ./test.proto > test-data.protob
/go/bin/protoscope test-data.protob 
/go/bin/protoscope /workspaces/antoine-eulisa/message-etias.dat 
