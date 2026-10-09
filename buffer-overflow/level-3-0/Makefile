TARGET = buffer-overflow-level3.0
CC     = gcc
CFLAGS = -Wall -Wextra
SECFLAGS = -no-pie -fno-stack-protector
# Embed libcrypto so the challenge does not require a particular OpenSSL SONAME.
LDLIBS = -Wl,-Bstatic -lcrypto -Wl,-Bdynamic

.PHONY: all clean

all: $(TARGET)

%: %.c
	$(CC) $(CFLAGS) $(SECFLAGS) $(LDFLAGS) -o $@ $< $(LDLIBS)

clean: 
	rm -rf $(TARGET)
