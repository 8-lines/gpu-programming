build/sph: main.cc theora.cc opengl.hh theora.hh vector.hh
	@mkdir -p build
	g++ -O3 -march=native -fopenmp $(shell pkg-config --cflags theoraenc glut glu gl glew) main.cc theora.cc -lOpenCL $(shell pkg-config --libs theoraenc glut glu gl glew) -o build/task5

run: build/task5
	Xvfb :123 -screen 0 800x600x24 &
	env DISPLAY=:123 ./build/task5

vglrun: build/task5
	env LD_LIBRARY_PATH=$(LIBRARY_PATH) vglrun ./build/task5

clean:
	rm -rf task5

.PHONY: run clean
