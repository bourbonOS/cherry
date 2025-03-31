SRC_DIR := src/synergy
BIN_NAME := synergy
OUTPUT_DIR := bin
INSTALL_DIR := /usr/bin

all: $(OUTPUT_DIR)/$(BIN_NAME)

$(OUTPUT_DIR)/$(BIN_NAME): $(SRC_DIR)
	mkdir -p $(OUTPUT_DIR)
	shc -f $(SRC_DIR) -o $(OUTPUT_DIR)/$(BIN_NAME)

install: $(OUTPUT_DIR)/$(BIN_NAME)
	install -m 755 $(OUTPUT_DIR)/$(BIN_NAME) $(INSTALL_DIR)

clean:
	rm -rf $(OUTPUT_DIR)

.PHONY: all install clean