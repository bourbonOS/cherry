SRC_DIR := src/synergy
BIN_NAME := synergy
OUTPUT_DIR := bin
INSTALL_DIR := /usr/bin

build: $(OUTPUT_DIR)/$(BIN_NAME)

$(OUTPUT_DIR)/$(BIN_NAME): $(SRC_DIR)
	mkdir -p $(OUTPUT_DIR)
	shc -f $(SRC_DIR) -o $(OUTPUT_DIR)/$(BIN_NAME)

install: build
	install -m 755 $(OUTPUT_DIR)/$(BIN_NAME) $(INSTALL_DIR)

.PHONY: build install
