SRC_DIR := src
BIN_DIR := /usr/bin
LIBEXEC_DIR := /usr/libexec/ostools
CONF_DIR := /etc/containerconf
SHC := shc

all: $(BIN_DIR)/cherry install_submodules install_configs

$(BIN_DIR)/cherry: $(SRC_DIR)/cherry
    $(SHC) -f $< -o $@
    @echo "Binary $@ created."

install_submodules: $(SRC_DIR)/submodules
    @mkdir -p $(LIBEXEC_DIR)
    @for file in $(SRC_DIR)/submodules/*; do \
        if [ -f $$file ]; then \
            binary_name=$$(basename $$file); \
            $(SHC) -f $$file -o $(LIBEXEC_DIR)/$$binary_name; \
            echo "Binary $(LIBEXEC_DIR)/$$binary_name created."; \
        fi \
    done

install_configs: $(SRC_DIR)/files
    @mkdir -p $(CONF_DIR)
    @for file in $(SRC_DIR)/files/*; do \
        if [ -f $$file ]; then \
            cp $$file $(CONF_DIR)/; \
            echo "File $$file installed to $(CONF_DIR)/."; \
        fi \
    done

install: all
    @echo "Installation complete."

clean:
    @rm -f $(BIN_DIR)/cherry
    @rm -f $(LIBEXEC_DIR)/*
    @rm -f $(CONF_DIR)/*
    @echo "Cleaned up generated files."

.PHONY: all install_submodules install_configs install clean