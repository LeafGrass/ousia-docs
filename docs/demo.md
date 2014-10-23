# Demo
Things always look pretty good if they'd go with a demo:

## on boot

	                 _
	 _              / /
	| |  ___  __ _ _| |_ __ _ _  __  __ _   _   _
	| | / _ \/ _` |_   _/ _` | \/ _)/ _` | / / / /
	| |_  __( (_| | | |  (_| | | | ( (_| | \ \ \ \
	|_ _\___|\__,_| | | \__, / | |  \__,_| /_/ /_/
	                /_/ \_ _/

	    Ousia v0.2.3 Himalayan-Monkshood
	            by LeafGrass - leafgrass.g@gmail.com

	Welcome to Ousia console. :)
	Please press ENTER to activate it.

## available commands list
	$ help
	available commands:
	    help
	    ?
	    debug
	    reboot
	    free
	    xd
	    mw

## memory statistics
	$ free
	              total       used       free    largest
	Mem:          12288       5200       7088       7088

## listing processes(threads)
	$ debug
	[   529.864] 5 processes in queue:
	[   529.899]    pid   pcb      state  prio      run      sleep   name
	[   529.969]     5  0x20002090   0      0       0.350    0.000   ps_console
	[   530.046]     3  0x20001b10   1      0       0.000    0.363   ps_main
	[   530.120]     1  0x20001490  -1      0       0.000    0.000   __cps_init
	[   530.196]     2  0x200016d0   2      0     529.210    0.000   __cps_idle
	[   530.273]     4  0x20001f50   2      0       0.000    0.000   ps_button

## memory dump
	$ xd 0x08005000 128
	argv[1]: 0x08005000
	argv[2]: 128
	argc: 3
	addr: 0x8005000
	nb: 128
	memory dump
	08005000: 00 50 00 20 51 51 00 08 f1 50 00 08 f5 50 00 08 .P. QQ...P...P..
	08005010: f9 50 00 08 fd 50 00 08 01 51 00 08 61 51 00 08 .P...P...Q..aQ..
	08005020: 61 51 00 08 61 51 00 08 61 51 00 08 69 81 00 08 aQ..aQ..aQ..i...
	08005030: 61 51 00 08 61 51 00 08 31 81 00 08 29 55 00 08 aQ..aQ..1...)U..
	08005040: 61 51 00 08 61 51 00 08 61 51 00 08 61 51 00 08 aQ..aQ..aQ..aQ..
	08005050: 61 51 00 08 61 51 00 08 b9 51 00 08 d9 51 00 08 aQ..aQ...Q...Q..
	08005060: f9 51 00 08 19 52 00 08 39 52 00 08 71 59 00 08 .Q...R..9R..qY..
	08005070: 89 59 00 08 a1 59 00 08 bd 59 00 08 d9 59 00 08 .Y...Y...Y...Y..

## abort handling
	$ xd 0x20005000 128
	argv[1]: 0x20005000
	argv[2]: 128
	argc: 3
	addr: 0x20005000
	nb: 128
	memory dump
	[   676.653] __hard_fault_handler - psp: 0x200027E0, exception number: 2
	[   676.653] xpsr: 0x21000000
	[   676.653] pc:   0x080097FA
	[   676.653] lr:   0x080097F9
	[   676.653] r12:  0x00000032
	[   676.653] r3:   0x20002800
	[   676.653] r2:   0x2000280A
	[   676.653] r1:   0x00000000
	[   676.653] r0:   0x0000000A
	[   676.653] r11:  0x00000000
	[   676.653] r10:  0x0800AB1C
	[   676.653] r9:   0x20005000
	[   676.653] r8:   0x00000080
	[   676.653] r7:   0x00000000
	[   676.653] r6:   0x200012C8
	[   676.653] r5:   0x08007900
	[   676.653] r4:   0x30303035
	[   676.653] >>> dump pcb: 0x20002090 <<<
	[   676.653] stack_ptr: 0x20002830
	[   676.653] pentry:    0x080093AD
	[   676.653] name:      ps_console
	[   676.653] stack_sz:  2048
	[   676.653] pid:       5
	[   676.653] prio:      0
	[   676.653] stat:      0
	[   676.653] tcb:       0x200020AC
	[   676.653] prev:      0x200010A0
	[   676.653] next:      0x20001B10
	[   676.653] ----------------------------
	[   676.653] 5 processes in queue:
	[   676.653]    pid   pcb      state  prio      run      sleep   name
	[   676.653]     5  0x20002090   0      0       2.644    0.000   ps_console
	[   676.653]     3  0x20001b10   1      0       0.000    0.201   ps_main
	[   676.653]     1  0x20001490  -1      0       0.000    0.000   __cps_init
	[   676.653]     2  0x200016d0   2      0     673.600    0.000   __cps_idle
	[   676.653]     4  0x20001f50   2      0       0.000    0.000   ps_button
