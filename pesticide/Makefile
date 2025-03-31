SRC_DIR := src
BIN_DIR := /usr/libexec/pesticide
CONF_DIR := /etc/pesticide.d
SHC := shc

SRC_FILES := $(wildcard $(SRC_DIR)/*)
BIN_FILES := $(patsubst $(SRC_DIR)/%, $(BIN_DIR)/%, $(SRC_FILES))
CONF_FILE := $(SRC_DIR)/files/pesticide.conf
INSTALLED_CONF := $(CONF_DIR)/pesticide.conf

all: $(BIN_FILES)

$(BIN_DIR)/%: $(SRC_DIR)/%
	mkdir -p $(BIN_DIR)
	$(SHC) -f $< -o $@

install: all $(INSTALLED_CONF)

$(INSTALLED_CONF): $(CONF_FILE)
	mkdir -p $(CONF_DIR)
	cp $< $@

clean:
	rm -rf $(BIN_DIR)

.PHONY: all install clean