Demo of ProtoBuf Usage
======================

#### 1. Create .proto file

#### 2. Download protobuf compiler
See https://github.com/os72/protoc-jar

#### 3. Generate protobuf code
SRC_DIR=/Users/yincaihua/github.com/caihua-yin/protobufdemo/src/main/proto
DST_DIR=/Users/yincaihua/github.com/caihua-yin/protobufdemo/src/main/java
/Users/yincaihua/github.com/protoc-jar/bin_241/mac/protoc -I=$SRC_DIR --java_out=$DST_DIR $SRC_DIR/addressbook.proto

*NOTE the protoc compiler version must be identical as the depenedency package version*, otherwise following exception will happen:
```
java.lang.UnsupportedOperationException: This is supposed to be overridden by subclasses.
```

#### 4. Update pom.xml to add dependency and maven-assembly-plugin 

#### 5. Download dependency and build package
```
mvn dependency:copy-dependencies
mvn package
```

#### 6. Add a person record
```
java -jar target/protobufdemo-1.0-jar-with-dependencies.jar phone_adderss_file
```

#### 7. List all records
```
java -cp target/protobufdemo-1.0-jar-with-dependencies.jar com.caihua.protobufdemo.ListPeople phone_adderss_file
```

#### Appendix
##### Run hello world App main function:
```
java -cp target/protobufdemo-1.0-jar-with-dependencies.jar com.caihua.protobufdemo.App
```
