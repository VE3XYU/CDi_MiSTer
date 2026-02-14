# Analysis of Lost Ride

@00407FB2(kernel)   Found cdi_LostRide module at $dd7710 (revision 1, crc $B1DE13, 125950 bytes)

4076ec

DVC ROM Addresses

00e52944 PSOrg  15018308
00e5297c PSPos  15018364
00e52a50 PSWndw 15018576

PSWndw
D3 0
D4 04800160    1152x352


PSOrg
D3 ff24005e
   ffe60038
   
setstt
  MV_Org = 0x10c   d3 H:V origin

00ded4ac Wrapper function for PSOrg / MV_Org?
  Called from d0879c (jump table?)
    Called from de279a (inside function FUN_00de2122) dez 14559130

When broken at the start
    de279a calls d0879c calls 00ded4ac

So what is the problem? A failing test?

00ded4ac is a wrapper function for MV_Org! The parameter D3 is taken from stack.

uVar2 = (*(code *)(unaff_A6 + 0x79c))((int)*(short *)(unaff_A6 + -0x320a),iVar1,0);

A6 = 0xBCA0

0x8a96 ?
