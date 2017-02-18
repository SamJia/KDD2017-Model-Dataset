exe = ctcd_ber
exe_poi = ctcd
cc = g++
objects = ./dataset_ber.o ./main_ber.o ./model_ber.o ./utils_ber.o
objects_poi = ./dataset.o ./main.o ./model.o ./utils.o
std = c++11

all : $(exe) $(exe_poi)

$(exe) : $(objects)
			$(cc) -O2 -fopenmp -std=$(std) -o $(exe) $(objects)
$(exe_poi) : $(objects_poi)
			$(cc) -O2 -fopenmp -std=$(std) -o $(exe_poi) $(objects_poi)

./dataset_ber.o : ./dataset.cc dataset.h
	$(cc) -std=$(std) -O2 -fopenmp -c ./dataset.cc -o ./dataset_ber.o
./main_ber.o : ./main.cc utils.h dataset.h main.h model.h
	$(cc) -std=$(std) -O2 -fopenmp -c ./main.cc -o ./main_ber.o
./model_ber.o : ./model.cc utils.h model.h dataset.h
	$(cc) -std=$(std) -O2 -fopenmp -c ./model.cc -o ./model_ber.o
./utils_ber.o : ./utils.cc utils.h
	$(cc) -std=$(std) -O2 -fopenmp -c ./utils.cc -o ./utils_ber.o

./dataset.o : ./dataset.cc dataset.h
	$(cc) -std=$(std) -O2 -DPOISSON -fopenmp -c ./dataset.cc -o ./dataset.o
./main.o : ./main.cc utils.h dataset.h main.h model.h
	$(cc) -std=$(std) -O2 -DPOISSON -fopenmp -c ./main.cc -o ./main.o
./model.o : ./model.cc utils.h model.h dataset.h
	$(cc) -std=$(std) -O2 -DPOISSON -fopenmp -c ./model.cc -o ./model.o
./utils.o : ./utils.cc utils.h
	$(cc) -std=$(std) -O2 -DPOISSON -fopenmp -c ./utils.cc -o ./utils.o

clean :
		rm $(objects) $(exe) $(objects_poi) $(exe_poi)
