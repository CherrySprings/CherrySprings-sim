CXX = g++
CFLAGS = -std=c++11 -Wall -c -fPIC 
LDFLAGS = -shared -lpthread -ldl -lz
SRC_DIR = csrc
BUILD_DIR = build
SOURCES = $(wildcard $(SRC_DIR)/*.cpp)
OBJECTS = $(SOURCES:$(SRC_DIR)/%.cpp=$(BUILD_DIR)/%.o)
TARGET = libdifftest.so

all: $(TARGET)

$(TARGET): $(OBJECTS)
	$(CXX) $(LDFLAGS) $^ -o $@

$(BUILD_DIR)/%.o: $(SRC_DIR)/%.cpp
	mkdir -p $(BUILD_DIR)
	$(CXX) $(CFLAGS) $< -o $@

clean:
	rm -rf $(BUILD_DIR)
	rm -f $(TARGET)

.PHONY: clean
