
panic(cpu 2 caller 0xfffffe001b2461d0): DCP PANIC - ASSERT!AppleDCPDPTXPowerController.cpp:561 No device added after powering on the rails. HPD=0 - dcpav(27)
ASSERT!AppleDCPDPTXPowerController.cpp:561 No device added after powering on the rails. HPD=0
RTKit: RTKit-2758.1.1.release - Client: AppleDCP-811.1.1~754-ipad14dcp.RELEASE
!UUID: a1000010-2140-1ed5-a178-80d201401ed5
ASLR slide: 0x0000000000369000
Time: 0x00000046330974f9

Faulting task  27 Call Stack: 0x000000000038bdc0 0x000000000038b780 0x000000000038b590 0x0000000000384000 0x00000000003df3f8 0x00000000003ed93c 0x00000000004c26fc 0x00000000004b31e8 0x000000000038c214 0x0000000000386c58 000000000000000000
RTKit Task List:
   name                    | pri     | stack use | status     | resource | warning
 0 rtk_background          | 007     |   824/2048  | SEMWAIT    | 0xca0d10 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

 1 rtk_ep_work             | 057     |   920/2048  | SEMWAIT    | 0xc9d430 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

 2 log_tx                  | 007     |   624/2048  | SEMWAIT    | 0xc89f50 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

 3 log_flush               | 015     |   848/4096  | SEMWAIT    | 0xc89250 | 
      0x0000000000386130 0x0000000000387098 0x00000000003931b0 0x0000000000386c58

 4 power                   | 000     |  1776/65536 | RUNNABLE   | 0xa51950 | 
      0x0000000000386130 0x000000000038afa0 0x000000000038ac84 0x0000000000386c58

 5 Terminator              | 015     |   416/2048  | SEMWAIT    | 0xffffffff4116fbd0 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

 6 main                    | 015     |  6992/40960 | SEMWAIT    | 0xc70170 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000376bf0 0x0000000000378de8

 7 dcpexpert               | 015     |   240/16368 | SEMWAIT    | 0xffffffff0c011f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

 8 AFKMailboxEndpoint      | 015     |   688/16368 | SEMWAIT    | 0xffffffff0c031f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

 9 rtkitpmgr               | 015     |   240/16368 | SEMWAIT    | 0xffffffff0c051f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

10 iomfb_driver            | 016     |  4272/16384 | SEMWAIT    | 0xffffffff4115b370 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

11 iomfb_low               | 009     |   240/16384 | SEMWAIT    | 0xffffffff41150fa0 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

12 iomfb_driver_low        | 008     |   240/16384 | SEMWAIT    | 0xffffffff41141a20 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

13 iomfb_cdfd              | 014     |  3808/16384 | SEMWAIT    | 0xffffffff41123020 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

14 iomfb_dcp_disp_serv     | 016     |  1008/4096  | SEMWAIT    | 0xffffffff411129c0 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

15 iomfb_ap_link           | 016     |  1200/4096  | SEMWAIT    | 0xffffffff411114b0 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

16 iomfb_ap_caller_0       | 016     |   240/512   | SEMWAIT    | 0xffffffff41110040 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

17 iomfb_ap_caller_1       | 016     |   240/512   | SEMWAIT    | 0xffffffff4110f900 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

18 iomfb_ap_caller_2       | 016     |   240/512   | SEMWAIT    | 0xffffffff4110f2d0 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

19 iomfb_ap_caller_3       | 016     |   240/512   | SEMWAIT    | 0xffffffff4110ec50 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

20 iomfb_ap_callee_0       | 016     |  6896/16384 | SEMWAIT    | 0xffffffff4110e5e0 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

21 iomfb_ap_callee_1       | 016     |  6688/16384 | SEMWAIT    | 0xffffffff4110a160 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

22 iomfb_ap_callee_2       | 016     |   240/16384 | SEMWAIT    | 0xffffffff41105cf0 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

23 iomfb_ap_callee_3       | 016     |   240/16384 | SEMWAIT    | 0xffffffff41101870 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

24 iosurface_tracker_timer | 015     |   240/16368 | SEMWAIT    | 0xffffffff0c071f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

25 AUCWorkLoop             | 015     |   240/16368 | SEMWAIT    | 0xffffffff0c091f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

26 auc_dcp_queue           | 015     |   288/16368 | WAITING    | 0xffffffff410f2170 | 
      0x0000000000386130 0x00000000003868f4 0x00000000003856dc 0x000000000038c8d0 0x00000000004b53a8 0x0000000000386c58

27 dcpav                   | 015     |  1072/16368 | RUNNABLE   | 0 | [Faulting task]

28 cpCapsThread            | 015     |  1360/16368 | SEMWAIT    | 0xffffffff0c0f1f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

29 additionThread          | 015     |  6960/16368 | SEMWAIT    | 0xffffffff0c111f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

30 removalThread           | 015     |   240/16368 | SEMWAIT    | 0xffffffff0c131f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

31 dcpav-power-epic        | 015     |   240/16368 | SEMWAIT    | 0xffffffff0c151f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

32 config                  | 015     |   736/16368 | WAITING    | 0xffffffff410cb0c8 | 
      0x0000000000386130 0x00000000003868f4 0x00000000003856dc 0x000000000038c8d0 0x00000000004b53a8 0x0000000000386c58

33 dcpdptx-hdcp-interface  | 015     |  2912/16368 | SEMWAIT    | 0xffffffff0c191f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

34 dcpav-controller-epic   | 015     |  2912/16368 | SEMWAIT    | 0xffffffff0c1b1f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

35 dcpdp-controller-epic   | 015     |   240/16368 | SEMWAIT    | 0xffffffff0c1d1f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

36 sac-controller          | 015     |   240/16368 | SEMWAIT    | 0xffffffff0c1f1f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

37 setDisplayAsync         | 015     |  1280/16368 | SEMWAIT    | 0xffffffff0c211f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

38 dcpav-sac-epic          | 015     |  2912/16368 | SEMWAIT    | 0xffffffff0c231f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

39 endpointWL              | 015     |  3504/8192  | SEMWAIT    | 0xffffffff410a0c80 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

40 md-manager              | 015     |  3568/8192  | SEMWAIT    | 0xffffffff4109dc30 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

41 AFKGlobalDispatch       | 015     |  7184/16368 | WAITING    | 0xffffffff41095398 | 
      0x0000000000386130 0x00000000003868f4 0x00000000003856dc 0x000000000038c8d0 0x00000000004b53a8 0x0000000000386c58

42 iomfb_alss              | 016     |   240/4096  | SEMWAIT    | 0xffffffff4102fc00 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

43 iomfb_pdc               | 008     |   240/4096  | SEMWAIT    | 0xffffffff41021820 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

44 iomfb_backlight         | 016     |   240/4096  | SEMWAIT    | 0xffffffff41000da0 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

45 iomfb_mailbox           | 018     |   384/16384 | SEMWAIT    | 0xffffffff40fff110 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

46 iomfb_mailbox_async     | 018     |   240/16384 | SEMWAIT    | 0xffffffff40fefaf0 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

47 iomfb_reg_stream        | 016     |   240/4096  | SEMWAIT    | 0xffffffff40fe7280 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

48 iomfb_video_async       | 016     |  5840/16384 | SEMWAIT    | 0xffffffff40fd6850 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

49 iomfb_video_if          | 016     |   240/4096  | SEMWAIT    | 0xffffffff40fd2250 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

50 iomfb_video_async       | 016     |   240/16384 | SEMWAIT    | 0xffffffff40fc5ae0 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

51 iomfb_video_if_stub     | 016     |   240/4096  | SEMWAIT    | 0xffffffff40fc1500 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

53 cp                      | 015     |   240/16368 | SEMWAIT    | 0xffffffff0c291f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

64 poweroff                | 015     |   240/16368 | SEMWAIT    | 0xffffffff0c311f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

65 cpsrc                   | 015     |   240/16368 | SEMWAIT    | 0xffffffff0c331f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

66 restartIntfc            | 015     |   240/16368 | SEMWAIT    | 0xffffffff0c491f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

67 hdmiErrorMonitor        | 015     |   240/16368 | SEMWAIT    | 0xffffffff0c4b1f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

68 termination             | 015     |  3056/16368 | WAITING    | 0xffffffff410fd2b0 | 
      0x0000000000386130 0x00000000003868f4 0x00000000003856dc 0x000000000038c8d0 0x00000000004b53a8 0x0000000000386c58

69 iomfb_mailbox           | 018     |   656/16384 | SEMWAIT    | 0xffffffff40f44640 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

70 iomfb_mailbox_async     | 018     |  4688/16384 | SEMWAIT    | 0xffffffff40f355b0 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

71 hdmiErrorInject         | 015     |   240/16368 | SEMWAIT    | 0xffffffff0c4d1f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

72 sinkCount               | 015     |   240/16368 | SEMWAIT    | 0xffffffff0c531f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

73 linkStatus              | 015     |   240/16368 | SEMWAIT    | 0xffffffff0c551f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

74 cpIrq                   | 015     |   240/16368 | SEMWAIT    | 0xffffffff0c571f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

75 dpIrq                   | 015     |  5648/16368 | SEMWAIT    | 0xffffffff0c371f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58

80 aup                     | 015     |   240/16368 | SEMWAIT    | 0xffffffff0c5b1f40 | 
      0x0000000000386130 0x0000000000387098 0x000000000038c1a8 0x0000000000386c58


Chinook ASC Async error info: 
l2c_err_sts 0x5000fbfc00000000, l2c_err_adr 000000000000000000, l2c_err_inf 000000000000000000
lsu_err_sts 000000000000000000, fed_err_sts 000000000000000000, mmu_err_sts 000000000000000000
dpc_err_sts 000000000000000000

Mailbox (0): (0)
  Inbox  AKF_KIC_INBOX_CTRL = 0x00020001, AKF_KIC_MAILBOX_SET = 0x11111101
  Outbox AKF_AP_OUTBOX_CTRL = 0x00020001, AKF_AP_MAILBOX_SET  = 0x00000000

    dir   endpoint      timestamp           msg
    ====  ============  ==================  ==================
    [TX]        user24  0x000000462be25cec  0x0000000000000642
    [TX]        syslog  0x000000462be260a0  0x005000000000000c
    [RX]        syslog  0x000000462be2647c  0x005000000000000c
    [TX]        user24  0x000000462be26e10  0x0000000000000242
    [TX]        user24  0x000000462be26f34  0x000000b000000302
    [RX]        user24  0x000000462be27238  0x0000001400000202
    [RX]        user24  0x000000462be272f8  0x0000000000000342
    [TX]        user24  0x000000462be27600  0x0000001c00000002
    [RX]        user24  0x000000462be27914  0x0000000000000042
    [TX]        syslog  0x000000462be27948  0x005000000000000d
    [TX]        user24  0x000000462be27ac4  0x0000000000000242
    [RX]        syslog  0x000000462be27dc8  0x005000000000000d
    [RX]        user24  0x000000462be34bac  0x0000002400000202
    [TX]        user24  0x000000462be35478  0x0000000000000242
    [RX]        user24  0x000000462be35eb8  0x0000001800000202
    [TX]        user24  0x000000462be36204  0x0000001c00000002
    [RX]        user24  0x000000462be36690  0x0000000000000042
    [TX]        user24  0x000000462be368b0  0x0000000000000242
    [RX]        user24  0x000000462be371b4  0x0000107c00000202
    [TX]        user24  0x000000462be376a4  0x0000000000000242
    [RX]        user24  0x000000462be37b78  0x0000107c00000202
    [TX]        user24  0x000000462be37ecc  0x0000000000000242
    [RX]        user24  0x000000462be384f8  0x0000107c00000202
    [TX]        user24  0x000000462be38858  0x0000000000000242
    [RX]        user24  0x000000462be38dd8  0x0000107c00000202
    [TX]        user24  0x000000462be397b8  0x0000000000000242
    [RX]        user24  0x000000462be39e78  0x0000107c00000202
    [TX]        user24  0x000000462be3a5c0  0x0000000000000242
    [RX]        user24  0x000000462be3ab08  0x0000107c00000202
    [TX]        user24  0x000000462be3b1dc  0x0000000000000242
    [RX]        user24  0x000000462be3b7b0  0x0000107c00000202
    [TX]        user24  0x000000462be3c0e0  0x0000000000000242
    [RX]        user24  0x000000462be3c668  0x0000107c00000202
    [RX]   ioreporting  0x000000462be3c684  0x0040000000000000
    [TX]        user24  0x000000462be3ca80  0x0000000000000242
    [RX]        user24  0x000000462be3cf60  0x0000107c00000202
    [TX]        user24  0x000000462be3d15c  0x0000000000000242
    [RX]        user24  0x000000462be3d528  0x0000107c00000202
    [TX]        user24  0x000000462be3dd9c  0x0000000000000242
    [RX]        user24  0x000000462be3e078  0x0000107c00000202
    [TX]        user24  0x000000462be3e83c  0x0000000000000242
    [RX]        user24  0x000000462be3eb04  0x0000107c00000202
    [TX]        user24  0x000000462be3ed34  0x0000000000000242
    [RX]        user24  0x000000462be3f110  0x0000107c00000202
    [TX]        user24  0x000000462be3f7c4  0x0000000000000242
    [RX]        user24  0x000000462be3fb5c  0x0000107c00000202
    [TX]        user24  0x000000462be40160  0x0000000000000242
    [RX]        user24  0x000000462be40420  0x0000107c00000202
    [TX]        user24  0x000000462be409b8  0x0000000000000242
    [RX]        user24  0x000000462be40cc8  0x0000107c00000202
    [TX]        user24  0x000000462be41464  0x0000000000000242
    [RX]        user24  0x000000462be417a4  0x0000107c00000202
    [TX]        user24  0x000000462be41a74  0x0000000000000242
    [RX]        user24  0x000000462be41d14  0x0000107c00000202
    [TX]        user24  0x000000462be41f04  0x0000000000000242
    [RX]        user24  0x000000462be42378  0x0000107c00000202
    [TX]        user24  0x000000462be425b0  0x0000000000000242
    [RX]        user24  0x000000462be428d8  0x0000107c00000202
    [TX]        user24  0x000000462be43140  0x0000000000000242
    [RX]        user24  0x000000462be43390  0x0000107c00000202
    [TX]        user24  0x000000462be43b3c  0x0000000000000242
    [RX]        user24  0x000000462be43e0c  0x0000107c00000202
    [TX]        user24  0x000000462be4454c  0x0000000000000242
    [RX]        user24  0x000000462be44800  0x0000107c00000202
    [TX]        user24  0x000000462be44e4c  0x0000000000000242
    [RX]        user24  0x000000462be450dc  0x0000107c00000202
    [TX]        user24  0x000000462be4536c  0x0000000000000242
    [RX]        user24  0x000000462be45620  0x0000107c00000202
    [TX]        user24  0x000000462be4590c  0x0000000000000242
    [RX]        user24  0x000000462be45c9c  0x0000107c00000202
    [TX]        user24  0x000000462be45ec0  0x0000000000000242
    [RX]        user24  0x000000462be461bc  0x0000107c00000202
    [TX]        user24  0x000000462be46878  0x0000000000000242
    [RX]        user24  0x000000462be46c2c  0x0000107c00000202
    [TX]        user24  0x000000462be47204  0x0000000000000242
    [RX]        user24  0x000000462be475a0  0x0000107c00000202
    [TX]        user24  0x000000462be47cc4  0x0000000000000242
    [RX]        user24  0x000000462be47fc8  0x0000107c00000202
    [TX]        user24  0x000000462be48780  0x0000000000000242
    [TX]   ioreporting  0x000000462be48914  0x0040000000000000
    [RX]        user24  0x000000462be48a84  0x0000107c00000202
    [TX]        user24  0x000000462be49104  0x0000000000000242
    [RX]        user24  0x000000462be495b8  0x0000107c00000202
    [TX]        user24  0x000000462be49aa8  0x0000000000000242
    [RX]        user24  0x000000462be4a038  0x0000107c00000202
    [TX]        user24  0x000000462be4ad24  0x0000000000000242
    [RX]        user24  0x000000462be4b1a4  0x0000107c00000202
    [TX]        user24  0x000000462be4b54c  0x0000000000000242
    [RX]        user24  0x000000462be4bff4  0x00001b7000000202
    [TX]        user24  0x000000462be4cf3c  0x0000000000000242
    [RX]        user24  0x000000462be63b40  0x0000002400000202
    [TX]        user24  0x000000462be64180  0x0000000000000242
    [RX]        user24  0x000000462be64984  0x0000001800000202
    [TX]        user24  0x000000462be64d0c  0x0000001c00000002
    [RX]        user24  0x000000462be65120  0x0000000000000042
    [TX]        user24  0x000000462be6548c  0x0000000000000242
    [RX]        user24  0x000000462be65e44  0x00001b7000000202
    [TX]        user24  0x000000462be66774  0x0000000000000242
    [RX]        user24  0x000000462be6b8f8  0x0000002400000202
    [TX]        user24  0x000000462be6bfa4  0x0000000000000242
    [RX]        user24  0x000000462be6c698  0x0000001800000202
    [TX]        user24  0x000000462be6c954  0x0000001c00000002
    [RX]        user24  0x000000462be6ce58  0x0000000000000042
    [TX]        user24  0x000000462be6d030  0x0000000000000242
    [RX]        user24  0x000000462be6dc64  0x0000001800000202
    [TX]        user24  0x000000462be6df14  0x0000001c00000002
    [RX]        user24  0x000000462be6e344  0x0000000000000042
    [TX]        user24  0x000000462be6e55c  0x0000000000000242
    [RX]        user24  0x000000462be6ed40  0x00001b7000000202
    [TX]        user24  0x000000462be6f690  0x0000000000000242
    [RX]        user24  0x000000462be74478  0x0000002400000202
    [TX]        user24  0x000000462be74734  0x0000000000000242
    [RX]        user24  0x000000462be74df0  0x0000002400000202
    [TX]        user24  0x000000462be74ff4  0x0000000000000242
    [RX]   ioreporting  0x000000462c3406a0  0x0040000000000000
    [TX]   ioreporting  0x000000462c3446b0  0x0040000000000000
    [RX]   ioreporting  0x000000462c347374  0x0040000000000000
    [TX]   ioreporting  0x000000462c34b5ec  0x0040000000000000
    [RX]   ioreporting  0x000000462c8136e4  0x0040000000000000
    [TX]   ioreporting  0x000000462c817814  0x0040000000000000
    [RX]        user24  0x000000462eb86014  0x0000001800000202
    [TX]        user24  0x000000462eb86560  0x0000000000000242
    [RX]        user24  0x000000462ecf61ac  0x0000001800000202
    [TX]        user24  0x000000462ecf64b0  0x0000000000000242
    [RX]   ioreporting  0x000000462efa9b28  0x0040000000000000
    [TX]   ioreporting  0x000000462efb0860  0x0040000000000000
    [RX]   ioreporting  0x000000463063f55c  0x0040000000000000
    [TX]   ioreporting  0x00000046306468ac  0x0040000000000000
No mapping found for coredump section: 0xffffffff0001d000 - 0xffffffff0001dfff
No mapping found for coredump section: 0xffffffff0001e000 - 0xffffffff0001efff
No mapping found for coredump section: 0xffffffff00137000 - 0xffffffff00176fff
No mapping found for coredump section: 0xffffffff00177000 - 0xffffffff0017dfff
No mapping found for coredump section: 0xffffffff0017e000 - 0xffffffff00184fff
No mapping found for coredump section: 0xffffffff00185000 - 0xffffffff0018bfff
No mapping found for coredump section: 0xffffffff0018c000 - 0xffffffff00192fff
No mapping found for coredump section: 0xffffffff00193000 - 0xffffffff00199fff
No mapping found for coredump section: 0xffffffff005ac000 - 0xffffffff005ebfff
No mapping found for coredump section: 0xffffffff005ec000 - 0xffffffff005f2fff
No mapping found for coredump section: 0xffffffff005f3000 - 0xffffffff005f9fff
No mapping found for coredump section: 0xffffffff005fa000 - 0xffffffff00600fff

Unknown Section: Section 'Cpct' [0x43706374], Version 1.0, size 64
0x5043546d 0x00000001 0x00000000 0x00000000 | mTCP............
0x00000000 0x00000000 0x00000000 0x00000000 | ................
0x00000000 0x00000000 0x00000000 0x00000000 | ................
0x00000000 0x00000000 0x00000000 0x00000000 | ................
Sleep Count: 2666974
Wake Count:  1324068
Duty Cycle:  2
Mailbox (1): (4)
  Inbox  AKF_KIC_INBOX_CTRL = 0x00020001, AKF_KIC_MAILBOX_SET = 0x11111101
  Outbox AKF_AP_OUTBOX_CTRL = 0x00020001, AP instance uninitialized


    dir   endpoint      timestamp           msg
    ====  ============  ==================  ==================
    [TX]        user01  0x000000462b5bf59c  0x6750313200040011
    [RX]        user01  0x000000462b5c14cc  0x0000000000000000
    [TX]        user01  0x000000462b932434  0x6750313200040011
    [RX]        user01  0x000000462b934700  0x0000000000000000
    [TX]        user01  0x000000462bb38194  0x6750306100040011
    [RX]        user01  0x000000462bb39a78  0x0000000000000000
    [TX]        user01  0x000000462be174f4  0x6750306100040011
    [RX]        user01  0x000000462be193d8  0x0000000000000000
Sleep Count: 2666974
Wake Count:  1324068
Duty Cycle:  2

RTBuddy(AP): Debug info:
_iopStatus = 0x8
_powerStateChangeLocked = false
Mailbox Status:
IDLE_STATUS: 0x000000ac
INBOX0_CTRL: 0x00020001
OUTBOX0_CTRL: 0x00021101
AP->IOP Mailbox Log:
Timestamp          | Dir  | Message
0x00000021fe902b64 | [RX] | Interrupt
0x00000021fe902bd0 | [RX] | 0x0000000000000242 0x0010010000000037
0x00000021fe9034ac | [TX] | 0x00001b7000000202 0x0000000000000037
0x00000021fe904578 | [RX] | Interrupt
0x00000021fe9045c4 | [RX] | 0x0000000000000242 0x0010010000000037
0x00000021fe91af60 | [TX] | 0x0000002400000202 0x0000000000000037
0x00000021fe91b7a0 | [RX] | Interrupt
0x00000021fe91b80c | [RX] | 0x0000000000000242 0x0010010000000037
0x00000021fe91be40 | [TX] | 0x0000001800000202 0x0000000000000037
0x00000021fe91c324 | [RX] | Interrupt
0x00000021fe91c33c | [RX] | 0x0000001c00000002 0x0010010000000037
0x00000021fe91c5e4 | [TX] | 0x0000000000000042 0x0000000000000037
0x00000021fe91caa0 | [RX] | Interrupt
0x00000021fe91caf8 | [RX] | 0x0000000000000242 0x0010010000000037
0x00000021fe91d2fc | [TX] | 0x00001b7000000202 0x0000000000000037
0x00000021fe91dd88 | [RX] | Interrupt
0x00000021fe91ddec | [RX] | 0x0000000000000242 0x0010010000000037
0x00000021fe922d04 | [TX] | 0x0000002400000202 0x0000000000000037
0x00000021fe9235bc | [RX] | Interrupt
0x00000021fe923600 | [RX] | 0x0000000000000242 0x0010010000000037
0x00000021fe923b50 | [TX] | 0x0000001800000202 0x0000000000000037
0x00000021fe923f68 | [RX] | Interrupt
0x00000021fe923fb8 | [RX] | 0x0000001c00000002 0x0010010000000037
0x00000021fe924310 | [TX] | 0x0000000000000042 0x0000000000000037
0x00000021fe924648 | [RX] | Interrupt
0x00000021fe9246b0 | [RX] | 0x0000000000000242 0x0010010000000037
0x00000021fe92511c | [TX] | 0x0000001800000202 0x0000000000000037
0x00000021fe925530 | [RX] | Interrupt
0x00000021fe925594 | [RX] | 0x0000001c00000002 0x0010010000000037
0x00000021fe925800 | [TX] | 0x0000000000000042 0x0000000000000037
0x00000021fe925b70 | [RX] | Interrupt
0x00000021fe925bb8 | [RX] | 0x0000000000000242 0x0010010000000037
0x00000021fe9261fc | [TX] | 0x00001b7000000202 0x0000000000000037
0x00000021fe926ca4 | [RX] | Interrupt
0x00000021fe926d18 | [RX] | 0x0000000000000242 0x0010010000000037
0x00000021fe92b898 | [TX] | 0x0000002400000202 0x0000000000000037
0x00000021fe92bd54 | [RX] | Interrupt
0x00000021fe92bdbc | [RX] | 0x0000000000000242 0x0010010000000037
0x00000021fe92c2ac | [TX] | 0x0000002400000202 0x0000000000000037
0x00000021fe92c61c | [RX] | Interrupt
0x00000021fe92c680 | [RX] | 0x0000000000000242 0x0010010000000037
0x00000021fedf7b58 | [TX] | 0x0040000000000000 0x0000000000000004
0x00000021fedfbcc4 | [RX] | Interrupt
0x00000021fedfbcdc | [RX] | 0x0040000000000000 0x0010010000000004
0x00000021fedfe5a4 | [TX] | 0x0040000000000000 0x0000000000000004
0x00000021fee02c00 | [RX] | Interrupt
0x00000021fee02c1c | [RX] | 0x0040000000000000 0x0010010000000004
0x00000021ff2ca8f0 | [TX] | 0x0040000000000000 0x0000000000000004
0x00000021ff2cee28 | [RX] | Interrupt
0x00000021ff2cee4c | [RX] | 0x0040000000000000 0x0010010000000004
0x000000220163d2ac | [TX] | 0x0000001800000202 0x0000000000000037
0x000000220163db78 | [RX] | Interrupt
0x000000220163dbdc | [RX] | 0x0000000000000242 0x0010010000000037
0x00000022017ad528 | [TX] | 0x0000001800000202 0x0000000000000037
0x00000022017adb24 | [RX] | Interrupt
0x00000022017adba0 | [RX] | 0x0000000000000242 0x0010010000000037
0x0000002201a60ea0 | [TX] | 0x0040000000000000 0x0000000000000004
0x0000002201a67e64 | [RX] | Interrupt
0x0000002201a67e8c | [RX] | 0x0040000000000000 0x0010010000000004
0x00000022030f64dc | [TX] | 0x0040000000000000 0x0000000000000004
0x00000022030fdf14 | [RX] | Interrupt
0x00000022030fdf50 | [RX] | 0x0040000000000000 0x0010010000000004
0x0000002205b5ec04 | [RX] | Interrupt
0x0000002205b5ecc0 | [RX] | 0x0010300806646000 0x0010010000000001
0x00000021fe8f6e20 | [RX] | 0x0000000000000242 0x0010560000000037
0x00000021fe8f712c | [TX] | 0x0000107c00000202 0x0000000000000037
0x00000021fe8f7778 | [RX] | Interrupt
0x00000021fe8f77dc | [RX] | 0x0000000000000242 0x0010670000000037
0x00000021fe8f79ec | [TX] | 0x0000107c00000202 0x0000000000000037
0x00000021fe8f7fcc | [RX] | Interrupt
0x00000021fe8f8018 | [RX] | 0x0000000000000242 0x0010780000000037
0x00000021fe8f8294 | [TX] | 0x0000107c00000202 0x0000000000000037
0x00000021fe8f8a78 | [RX] | Interrupt
0x00000021fe8f8b20 | [RX] | 0x0000000000000242 0x0010890000000037
0x00000021fe8f8d74 | [TX] | 0x0000107c00000202 0x0000000000000037
0x00000021fe8f908c | [RX] | Interrupt
0x00000021fe8f90d8 | [RX] | 0x0000000000000242 0x00109a0000000037
0x00000021fe8f92e4 | [TX] | 0x0000107c00000202 0x0000000000000037
0x00000021fe8f9524 | [RX] | Interrupt
0x00000021fe8f9584 | [RX] | 0x0000000000000242 0x0010ab0000000037
0x00000021fe8f9944 | [TX] | 0x0000107c00000202 0x0000000000000037
0x00000021fe8f9bc8 | [RX] | Interrupt
0x00000021fe8f9c24 | [RX] | 0x0000000000000242 0x0010bc0000000037
0x00000021fe8f9ea8 | [TX] | 0x0000107c00000202 0x0000000000000037
0x00000021fe8fa758 | [RX] | Interrupt
0x00000021fe8fa76c | [RX] | 0x0000000000000242 0x0010cd0000000037
0x00000021fe8fa958 | [TX] | 0x0000107c00000202 0x0000000000000037
0x00000021fe8fb150 | [RX] | Interrupt
0x00000021fe8fb1b0 | [RX] | 0x0000000000000242 0x0010de0000000037
0x00000021fe8fb3dc | [TX] | 0x0000107c00000202 0x0000000000000037
0x00000021fe8fbb64 | [RX] | Interrupt
0x00000021fe8fbbac | [RX] | 0x0000000000000242 0x0010ef0000000037
0x00000021fe8fbdcc | [TX] | 0x0000107c00000202 0x0000000000000037
0x00000021fe8fc460 | [RX] | Interrupt
0x00000021fe8fc4bc | [RX] | 0x0000000000000242 0x0010f00000000037
0x00000021fe8fc6ac | [TX] | 0x0000107c00000202 0x0000000000000037
0x00000021fe8fc97c | [RX] | Interrupt
0x00000021fe8fc9e0 | [RX] | 0x0000000000000242 0x0010010000000037
0x00000021fe8fcbec | [TX] | 0x0000107c00000202 0x0000000000000037
0x00000021fe8fcf24 | [RX] | Interrupt
0x00000021fe8fcf74 | [RX] | 0x0000000000000242 0x0010120000000037
0x00000021fe8fd270 | [TX] | 0x0000107c00000202 0x0000000000000037
0x00000021fe8fd4d8 | [RX] | Interrupt
0x00000021fe8fd53c | [RX] | 0x0000000000000242 0x0010230000000037
0x00000021fe8fd790 | [TX] | 0x0000107c00000202 0x0000000000000037
0x00000021fe8fde90 | [RX] | Interrupt
0x00000021fe8fdedc | [RX] | 0x0000000000000242 0x0010340000000037
0x00000021fe8fe1f0 | [TX] | 0x0000107c00000202 0x0000000000000037
0x00000021fe8fe814 | [RX] | Interrupt
0x00000021fe8fe898 | [RX] | 0x0000000000000242 0x0010450000000037
0x00000021fe8feb68 | [TX] | 0x0000107c00000202 0x0000000000000037
0x00000021fe8ff2dc | [RX] | Interrupt
0x00000021fe8ff32c | [RX] | 0x0000000000000242 0x0010560000000037
0x00000021fe8ff598 | [TX] | 0x0000107c00000202 0x0000000000000037
0x00000021fe8ffd98 | [RX] | Interrupt
0x00000021fe8ffdf8 | [RX] | 0x0000000000000242 0x0010670000000037
0x00000021fe8fff24 | [RX] | Interrupt
0x00000021fe8fff30 | [RX] | 0x0040000000000000 0x0010780000000004
0x00000021fe90004c | [TX] | 0x0000107c00000202 0x0000000000000037
0x00000021fe90075c | [RX] | Interrupt
0x00000021fe9007b0 | [RX] | 0x0000000000000242 0x0010890000000037
0x00000021fe9009f0 | [TX] | 0x0000107c00000202 0x0000000000000037
0x00000021fe9010bc | [RX] | Interrupt
0x00000021fe9010dc | [RX] | 0x0000000000000242 0x00109a0000000037
0x00000021fe9013f0 | [TX] | 0x0000107c00000202 0x0000000000000037
0x00000021fe90233c | [RX] | Interrupt
0x00000021fe902364 | [RX] | 0x0000000000000242 0x0010010000000037
0x00000021fe90265c | [TX] | 0x0000107c00000202 0x0000000000000037

Debugger message: panic
Memory ID: 0xff
OS release type: User
OS version: 24A348
Kernel version: Darwin Kernel Version 24.0.0: Tue Sep 24 23:37:13 PDT 2024; root:xnu-11215.1.12~1/RELEASE_ARM64_T8112
Fileset Kernelcache UUID: 237F707F2C936284529E815DC95EF785
Kernel UUID: F4857C35-8D59-3CDF-BC96-2E1692409CB7
Boot session UUID: 0CEFCADB-EF4D-4817-A7B8-95E1F708B9C1
iBoot version: iBoot-11881.1.1
secure boot?: YES
roots installed: 0
Paniclog version: 14
KernelCache slide: 0x000000000fbf0000
KernelCache base:  0xfffffe0016bf4000
Kernel slide:      0x000000000fbf8000
Kernel text base:  0xfffffe0016bfc000
Kernel text exec slide: 0x00000000112e0000
Kernel text exec base:  0xfffffe00182e4000
mach_absolute_time: 0x220b764ad9
Epoch Time:        sec       usec
  Boot    : 0x6781eb7a 0x00002fcb
  Sleep   : 0x67821c15 0x0002a5a3
  Wake    : 0x67821c82 0x0003ca1b
  Calendar: 0x67821c8b 0x000e1fad

Zone info:
  Zone map: 0xfffffe1b238dc000 - 0xfffffe3b238dc000
  . VM    : 0xfffffe1b238dc000 - 0xfffffe1ff05a8000
  . RO    : 0xfffffe1ff05a8000 - 0xfffffe2189f40000
  . GEN0  : 0xfffffe2189f40000 - 0xfffffe2656c0c000
  . GEN1  : 0xfffffe2656c0c000 - 0xfffffe2b238d8000
  . GEN2  : 0xfffffe2b238d8000 - 0xfffffe2ff05a4000
  . GEN3  : 0xfffffe2ff05a4000 - 0xfffffe34bd270000
  . DATA  : 0xfffffe34bd270000 - 0xfffffe3b238dc000
  Metadata: 0xfffffe1b1a2ec000 - 0xfffffe1b222ec000
  Bitmaps : 0xfffffe1b222ec000 - 0xfffffe1b238cc000
  Extra   : 0 - 0

CORE 0 recently retired instr at 0xfffffe001849be04
CORE 1 recently retired instr at 0xfffffe001849be04
CORE 2 recently retired instr at 0xfffffe001849a6b4
CORE 3 recently retired instr at 0xfffffe001849be04
CORE 4 recently retired instr at 0xfffffe001849be04
CORE 5 recently retired instr at 0xfffffe001849be04
CORE 6 recently retired instr at 0xfffffe001849be04
CORE 7 recently retired instr at 0xfffffe001849be04
TPIDRx_ELy = {1: 0xfffffe2b2330bf80  0: 0x0000000000000002  0ro: 0x0000000000000000 }
CORE 0 PVH locks held: None
CORE 1 PVH locks held: None
CORE 2 PVH locks held: None
CORE 3 PVH locks held: None
CORE 4 PVH locks held: None
CORE 5 PVH locks held: None
CORE 6 PVH locks held: None
CORE 7 PVH locks held: None
CORE 0: PC=0x000000018cd95840, LR=0x0000000190325178, FP=0x000000016b4b49e0
CORE 1: PC=0xfffffe001837a85c, LR=0xfffffe001837a85c, FP=0xfffffe1a28a47ed0
CORE 2 is the one that panicked. Check the full backtrace for details.
CORE 3: PC=0xfffffe00184965b0, LR=0xfffffe00184965ac, FP=0xfffffe1a29aebe40
CORE 4: PC=0xfffffe001837a860, LR=0xfffffe001837a85c, FP=0xfffffe1a2a3dbed0
CORE 5: PC=0xfffffe001837a85c, LR=0xfffffe001837a85c, FP=0xfffffe1a290fbed0
CORE 6: PC=0xfffffe001837a85c, LR=0xfffffe001837a85c, FP=0xfffffe1a2a76fed0
CORE 7: PC=0xfffffe001837a85c, LR=0xfffffe001837a85c, FP=0xfffffe1a29f3bed0
Compressor Info: 18% of compressed pages limit (OK) and 11% of segments limit (OK) with 2 swapfiles and OK swap space
Panicked task 0xfffffe2b2396b2d8: 0 pages, 530 threads: pid 0: kernel_task
Panicked thread: 0xfffffe2b2330bf80, backtrace: 0xfffffe1a29ffb810, tid: 951
		  lr: 0xfffffe001833ef3c  fp: 0xfffffe1a29ffb8a0
		  lr: 0xfffffe0018492610  fp: 0xfffffe1a29ffb910
		  lr: 0xfffffe00184909f0  fp: 0xfffffe1a29ffb9c0
		  lr: 0xfffffe00182eb8b0  fp: 0xfffffe1a29ffb9d0
		  lr: 0xfffffe001833e854  fp: 0xfffffe1a29ffbda0
		  lr: 0xfffffe0018b927cc  fp: 0xfffffe1a29ffbdc0
		  lr: 0xfffffe001b2461d0  fp: 0xfffffe1a29ffbe50
		  lr: 0xfffffe001ac4b298  fp: 0xfffffe1a29ffbe80
		  lr: 0xfffffe0018a8e144  fp: 0xfffffe1a29ffbed0
		  lr: 0xfffffe0018a8ed20  fp: 0xfffffe1a29ffbf20
		  lr: 0xfffffe00182f4be8  fp: 0x0000000000000000
      Kernel Extensions in backtrace:
         com.apple.driver.IOSlaveProcessor(1.0)[7041977D-27BD-3FD2-A437-16DD6B6A447F]@0xfffffe001ac4a120->0xfffffe001ac4bad3
         com.apple.driver.RTBuddy(1.0)[195CCE0C-407C-34B3-A3E8-6A236B4240D9]@0xfffffe001b21f060->0xfffffe001b260c13
            dependency: com.apple.driver.AppleA7IOP(1.0.2)[1B458BBB-D3C2-3E6F-ADE9-A5A1D3978F62]@0xfffffe0018c8d1b0->0xfffffe0018c93323
            dependency: com.apple.driver.AppleARMPlatform(1.0.2)[B0D2E9D2-A720-3F97-95F2-ABEED72C3D12]@0xfffffe0018d1e770->0xfffffe0018d72597
            dependency: com.apple.driver.IOSlaveProcessor(1)[7041977D-27BD-3FD2-A437-16DD6B6A447F]@0xfffffe001ac4a120->0xfffffe001ac4bad3
            dependency: com.apple.iokit.IOReportFamily(47)[28565B1F-7B9D-3BF5-BF9D-374568AE4C86]@0xfffffe001aba4e90->0xfffffe001aba7c93
            dependency: com.apple.kec.corecrypto(14.0)[D2B32A44-84CC-3567-AF2E-C465EA34E7E3]@0xfffffe001b588340->0xfffffe001b5e106b

last started kext at 698299817: com.apple.filesystems.autofs	3.0 (addr 0xfffffe0017736e80, size 5847)
loaded kexts:
com.apple.filesystems.autofs	3.0
com.apple.driver.AppleTopCaseHIDEventDriver	8400.24
com.apple.driver.CoreKDL	1
com.apple.driver.AppleBiometricServices	1
com.apple.driver.DiskImages.ReadWriteDiskImage	493.0.0
com.apple.driver.DiskImages.UDIFDiskImage	493.0.0
com.apple.driver.DiskImages.RAMBackingStore	493.0.0
com.apple.driver.DiskImages.FileBackingStore	493.0.0
com.apple.driver.AppleThunderboltIP	4.0.3
com.apple.driver.AppleUSBDeviceNCM	5.0.0
com.apple.driver.AppleFileSystemDriver	3.0.1
com.apple.AppleFSCompression.AppleFSCompressionTypeZlib	1.0.0
com.apple.AppleFSCompression.AppleFSCompressionTypeDataless	1.0.0d1
com.apple.nke.l2tp	1.9
com.apple.filesystems.tmpfs	1
com.apple.driver.SEPHibernation	1
com.apple.filesystems.nfs	1
com.apple.filesystems.lifs	1
com.apple.filesystems.apfs	2313.1.2
com.apple.IOTextEncryptionFamily	1.0.0
com.apple.filesystems.hfs.kext	672
com.apple.security.BootPolicy	1
com.apple.BootCache	40
com.apple.AppleEmbeddedSimpleSPINORFlasher	1
com.apple.driver.AppleALSColorSensor	1.0.0d1
com.apple.driver.AppleSmartBatteryManager	161.0.0
com.apple.driver.AudioDMAController-T8112	400.97
com.apple.driver.AppleAOPVoiceTrigger	400.40
com.apple.driver.AppleAVD	798.2
com.apple.driver.usb.AppleSynopsysUSB40XHCI	1
com.apple.driver.AppleSmartIO2	1
com.apple.driver.AppleMobileDispH14G-DCP	140.0
com.apple.driver.AppleJPEGDriver	7.1.5
com.apple.driver.AppleAVE2	803.16.2
com.apple.driver.AppleCS42L84Audio	800.93
com.apple.driver.AppleTypeCRetimer	1.0.0
com.apple.driver.AppleProResHW	425.3
com.apple.AGXG14G	320.35.5
com.apple.driver.ApplePMP	1
com.apple.driver.AppleSN012776Amp	800.93
com.apple.driver.AppleT8020SOCTuner	1
com.apple.driver.AppleT8112CLPC	1
com.apple.driver.AppleSamsungSerial	1.0.0d1
com.apple.driver.AppleSerialShim	1
com.apple.driver.AppleEventLogHandler	1
com.apple.driver.ApplePMPFirmware	1
com.apple.driver.AppleS5L8960XNCO	1
com.apple.driver.AppleDPDisplayTCON	1
com.apple.driver.AppleT8112PMGR	1
com.apple.driver.AppleS8000AES	1
com.apple.driver.AppleS8000DWI	1.0.0d1
com.apple.driver.AppleInterruptControllerV2	1.0.0d1
com.apple.driver.AppleT8110DART	1
com.apple.driver.AppleBluetoothModule	1
com.apple.driver.AppleBCMWLANBusInterfacePCIe	1
com.apple.driver.AppleS5L8920XPWM	1.0.0d1
com.apple.driver.AppleS5L8940XI2C	1.0.0d2
com.apple.driver.AppleSPIMC	1
com.apple.driver.AppleM68Buttons	1.0.0d1
com.apple.driver.AppleT8110	1
com.apple.iokit.IOUserEthernet	1.0.1
com.apple.driver.usb.AppleUSBUserHCI	1
com.apple.iokit.IOKitRegistryCompatibility	1
com.apple.iokit.EndpointSecurity	1
com.apple.driver.AppleDiskImages2	379.0.11
com.apple.AppleSystemPolicy	2.0.0
com.apple.kec.InvalidateHmac	1
com.apple.kec.AppleEncryptedArchive	1
com.apple.driver.driverkit.serial	6.0.0
com.apple.driver.AppleHSBluetoothDriver	8400.24
com.apple.driver.IOBluetoothHIDDriver	9.0.0
com.apple.driver.AppleHIDKeyboard	8000.4
com.apple.driver.AppleActuatorDriver	8400.33
com.apple.driver.AppleMultitouchDriver	8400.33
com.apple.driver.AppleMesaSEPDriver	100.99
com.apple.iokit.IOBiometricFamily	1
com.apple.iokit.IOAVBFamily	1300.26
com.apple.driver.DiskImages.KernelBacked	493.0.0
com.apple.driver.AppleXsanScheme	3
com.apple.driver.usb.networking	5.0.0
com.apple.driver.AppleThunderboltUSBDownAdapter	1.0.4
com.apple.driver.AppleThunderboltDPInAdapter	8.5.1
com.apple.driver.AppleThunderboltDPAdapterFamily	8.5.1
com.apple.driver.AppleThunderboltPCIDownAdapter	4.1.1
com.apple.nke.ppp	1.9
com.apple.driver.AppleConvergedIPCOLYBTControl	1
com.apple.driver.AppleConvergedPCI	1
com.apple.driver.AppleBluetoothDebug	1
com.apple.driver.AppleSEPHDCPManager	1.0.1
com.apple.driver.AppleTrustedAccessory	1
com.apple.iokit.AppleSEPGenericTransfer	1
com.apple.driver.AppleBTM	1.0.1
com.apple.driver.AppleDCPDPTXProxy	1.0.0
com.apple.driver.DCPDPFamilyProxy	1
com.apple.driver.AppleBSDKextStarter	3
com.apple.kext.triggers	1.0
com.apple.driver.IOHIDPowerSource	1
com.apple.driver.AppleCallbackPowerSource	1
com.apple.filesystems.hfs.encodings.kext	1
com.apple.driver.AppleDiagnosticDataAccessReadOnly	1.0.0
com.apple.driver.AppleSyntheticGameController	12.0.37
com.apple.driver.AppleHPM	3.4.4
com.apple.driver.AppleHIDTransportFIFO	8000.26
com.apple.driver.AppleHIDTransport	8000.26
com.apple.driver.AppleInputDeviceSupport	8000.26
com.apple.driver.AppleDockChannel	1
com.apple.AGXFirmwareKextG14GRTBuddy	1
com.apple.AGXFirmwareKextRTBuddy64	320.35.5
com.apple.driver.AppleAOPAudio	400.9
com.apple.driver.AppleUSBXDCIARM	1.0
com.apple.driver.AppleUSBXDCI	1.0
com.apple.iokit.IOUSBDeviceFamily	2.0.0
com.apple.driver.AppleT8112TypeCPhy	1
com.apple.driver.AppleT8103TypeCPhy	1
com.apple.driver.usb.AppleSynopsysUSBXHCI	1
com.apple.driver.usb.AppleUSBXHCI	1.2
com.apple.driver.AppleEmbeddedUSBHost	1
com.apple.driver.usb.AppleUSBHub	1.2
com.apple.driver.usb.AppleUSBHostCompositeDevice	1.2
com.apple.driver.AppleStockholmControl	1.0.0
com.apple.driver.AppleSPMIPMU	1.0.1
com.apple.driver.AppleDialogPMU	1.0.1
com.apple.driver.AppleSPMI	1.0.1
com.apple.driver.DCPAVFamilyProxy	1
com.apple.iokit.IONVMeFamily	2.1.0
com.apple.driver.AppleNANDConfigAccess	1.0.0
com.apple.plugin.IOgPTPPlugin	1300.51
com.apple.iokit.IOMobileGraphicsFamily-DCP	343.0.0
com.apple.iokit.IOMobileGraphicsFamily	343.0.0
com.apple.driver.AppleM2ScalerCSCDriver	265.0.0
com.apple.driver.AppleDCP	1
com.apple.driver.AppleCSEmbeddedAudio	800.93
com.apple.driver.AppleH11ANEInterface	8.18.0
com.apple.iokit.IOGPUFamily	104.0.6
com.apple.driver.AppleH13CameraInterface	9.7.0
com.apple.driver.AppleEmbeddedAudio	800.93
com.apple.iokit.AppleARMIISAudio	400.22
com.apple.driver.IISAudioIsolatedStreamECProxy	400.22
com.apple.driver.ExclavesAudioKext	200.54
com.apple.driver.AppleSART	1
com.apple.driver.ApplePassthroughPPM	3.0
com.apple.driver.AppleSPU	1
com.apple.driver.usb.AppleUSBHostPacketFilter	1.0
com.apple.driver.AppleFirmwareKit	1
com.apple.driver.ApplePMGR	1
com.apple.driver.AppleA7IOP-ASCWrap-v4	1.0.2
com.apple.driver.AppleARMWatchdogTimer	1
com.apple.driver.AppleDisplayCrossbar	1.0.0
com.apple.iokit.IODisplayPortFamily	1.0.0
com.apple.driver.AppleTypeCPhy	1
com.apple.driver.AppleA7IOP-MXWrap-v1	1.0.2
com.apple.driver.AppleThunderboltNHI	7.2.81
com.apple.driver.AppleT8103PCIeC	1
com.apple.iokit.IOThunderboltFamily	9.3.3
com.apple.iokit.IOPortFamily	1.0
com.apple.driver.ApplePIODMA	1
com.apple.driver.AppleT8112PCIe	1
com.apple.driver.AppleBluetoothDebugService	1
com.apple.driver.AppleBCMWLANCore	1.0.0
com.apple.iokit.IO80211Family	1200.13.1
com.apple.driver.IOImageLoader	1.0.0
com.apple.driver.AppleOLYHAL	1
com.apple.driver.AppleMCA2-T8112	900.4
com.apple.driver.AppleEmbeddedAudioLibs	400.9
com.apple.driver.AppleFirmwareUpdateKext	1
com.apple.driver.AppleGPIOICController	1.0.2
com.apple.driver.AppleMobileApNonce	1
com.apple.driver.AppleFireStormErrorHandler	1
com.apple.driver.AppleMultiFunctionManager	1
com.apple.driver.corecapture	1.0.4
com.apple.driver.AppleEmbeddedPCIE	1
com.apple.iokit.IOTimeSyncFamily	1300.51
com.apple.driver.DiskImages	493.0.0
com.apple.iokit.IOGraphicsFamily	598
com.apple.iokit.IOBluetoothFamily	9.0.0
com.apple.driver.AppleUIO	1
com.apple.driver.AppleSSE	1.0
com.apple.driver.AppleSEPKeyStore	2
com.apple.driver.AppleUSBTDM	556
com.apple.iokit.IOUSBMassStorageDriver	250
com.apple.iokit.IOPCIFamily	2.9
com.apple.iokit.IOUSBHostFamily	1.2
com.apple.driver.AppleUSBHostMergeProperties	1.2
com.apple.driver.usb.AppleUSBCommon	1.0
com.apple.driver.AppleSMC	3.1.9
com.apple.driver.RTBuddy	1.0.0
com.apple.driver.AppleEmbeddedTempSensor	1.0.0
com.apple.driver.AppleARMPMU	1.0
com.apple.iokit.IOAccessoryManager	1.0.0
com.apple.driver.AppleOnboardSerial	1.0
com.apple.iokit.IOSerialFamily	11
com.apple.iokit.IOSCSIBlockCommandsDevice	498
com.apple.iokit.IOSCSIArchitectureModelFamily	498
com.apple.driver.AppleRSMChannel	1
com.apple.iokit.IORSMFamily	1
com.apple.driver.AppleLockdownMode	1
com.apple.driver.AppleIPAppender	1.0
com.apple.iokit.IOSkywalkFamily	1.0
com.apple.driver.mDNSOffloadUserClient	1.0.1b8
com.apple.iokit.IONetworkingFamily	3.4
com.apple.driver.AppleFDEKeyStore	28.30
com.apple.driver.AppleEffaceableStorage	1.0
com.apple.driver.AppleCredentialManager	1.0
com.apple.driver.AppleSEPManager	1.0.1
com.apple.driver.IODARTFamily	1
com.apple.driver.AppleA7IOP	1.0.2
com.apple.driver.IOSlaveProcessor	1
com.apple.driver.AppleBiometricSensor	2
com.apple.iokit.IOHIDFamily	2.0.0
com.apple.AUC	1.0
com.apple.iokit.IOSurface	372.1
com.apple.iokit.IOAVFamily	1.0.0
com.apple.iokit.IOHDCPFamily	1.0.0
com.apple.iokit.IOCECFamily	1
com.apple.iokit.IOAudio2Family	1.0
com.apple.driver.AppleIISController	400.1
com.apple.driver.AppleAudioClockLibs	400.9
com.apple.driver.FairPlayIOKit	72.10.0
com.apple.driver.AppleARMPlatform	1.0.2
com.apple.iokit.IOSlowAdaptiveClockingFamily	1.0.0
com.apple.iokit.IOReportFamily	47
com.apple.security.quarantine	4
com.apple.security.sandbox	300.0
com.apple.iokit.IOStorageFamily	2.1
com.apple.kext.AppleMatch	1.0.0d1
com.apple.driver.AppleMobileFileIntegrity	1.0.5
com.apple.iokit.CoreAnalyticsFamily	1
com.apple.security.AppleImage4	7.0.0
com.apple.kext.CoreTrust	1
com.apple.iokit.IOCryptoAcceleratorFamily	1.0.1
com.apple.kec.pthread	1
com.apple.kec.Libm	1
com.apple.kec.Compression	1.0
com.apple.kec.corecrypto	14.0



** Stackshot Succeeded ** Bytes Traced 538467 (Uncompressed 1385552) **
