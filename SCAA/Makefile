JC = javac
JA = java

default: build-run

build-run:
	make clean && make compile-extractor && make run-calculator && make run-extractor

calculator:
	make clean && make compile-calculator && make run-calculator

extractor:
	make clean && make compile-extractor && make run-extractor

clean: 
	$(RM) -r ./bin && mkdir ./bin

compile-calculator: 
	$(JC) ./src/FeatureCalculators.java ./src/Util.java -sourcepath src/ -classpath .:weka.jar:commons.io_2.0.1.jar:javascv.jar:commons-lang3-3.3.2.jar:commons-exec-1.2.jar -g -d ./bin
	
compile-extractor:
	$(JC) src/FeatureExtractor.java src/Util.java src/BigramExtractor.java src/FeatureCalculators.java src/DepthASTNode.java src/WholeWordIndexFinder.java src/IndexWrapper.java -sourcepath src/ -classpath .:weka.jar:commons.io_2.0.1.jar:javascv.jar:commons-lang3-3.3.2.jar:commons-exec-1.2.jar -d ./bin
	
run-calculator:
	$(JA) -classpath ./bin:commons-exec-1.2.jar:weka.jar:commons.io_2.0.1.jar:commons-lang3-3.3.2.jar:javacsv.jar FeatureCalculators

run-extractor:
	$(JA) -classpath ./bin:commons-exec-1.2.jar:weka.jar:commons.io_2.0.1.jar:commons-lang3-3.3.2.jar:javacsv.jar FeatureExtractor
	
