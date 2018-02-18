CFLAGS = -Wall -O2 -g
CFLAGS_LOCAL = -Wall -O2 -g -I. -I../..
OBJ = dvb_print_si dvb_gen_si dvb_ecmg dvb_ecmg_test mpeg_print_pcr rtp_check_seqnum mpeg_restamp

ifeq "$(shell uname -s)" "Linux"
LDFLAGS += -lrt
endif

ifeq "$(shell uname -s)" "Darwin"
LDFLAGS += -liconv
endif

all: $(OBJ)

%: %.c
	$(CC) $(CFLAGS) $(LDFLAGS) -o $@ $<

local: CFLAGS = $(CFLAGS_LOCAL)
local: all

clean:
	rm -rf $(OBJ) *.dSYM
