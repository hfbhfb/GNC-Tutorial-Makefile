cpp_srcs := $(shell find src -name *.cpp)
cpp_objs := $(patsubst src/%.cpp,objs/%.o,$(cpp_srcs))
LDFLAGS = -std=c++11

objs/%.o : src/%.cpp
	@mkdir -p $(dir $@)
	@g++ -c $^ -o $@

all: clean run
	@echo all

workspace/exec : $(cpp_objs)
	g++ $^ -o $@

run : workspace/exec
	@./$<

clean :
	@rm -rf objs src/*.o
	@rm -rf objs workspace/exec

debug :
	@echo $(as_files)

.PHONY : debug run clean 