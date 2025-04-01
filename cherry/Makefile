SRC_DIR := src
BIN_DIR := /usr/bin
LIBEXEC_DIR := /usr/libexec/ostools
CONF_DIR := /etc/containerconf
SHC := shc

build:
    @mkdir -p $(LIBEXEC_DIR)
    $(SHC) -f $(SRC_DIR)/cherry -o $(BIN_DIR)/cherry
    @echo "Binary $(BIN_DIR)/cherry created."
    @for file in $(SRC_DIR)/submodules/*; do \
        if [ -f $$file ]; then \
            binary_name=$$(basename $$file); \
            $(SHC) -f $$file -o $(LIBEXEC_DIR)/$$binary_name; \
            echo "Binary $(LIBEXEC_DIR)/$$binary_name created."; \
        fi \
    done

install: build
    @mkdir -p $(CONF_DIR)
    @for file in $(SRC_DIR)/files/*; do \
        if [ -f $$file ]; then \
            cp $$file $(CONF_DIR)/; \
            echo "File $$file installed to $(CONF_DIR)/."; \
        fi \
    done
    @echo "Installation complete."

.PHONY: build install
