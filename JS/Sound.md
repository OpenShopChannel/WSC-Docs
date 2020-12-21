# Sound

You access it with the `wiiSound` object. Until this documentation is updated, please see the following:

```c
iVar2 = MSL_C.PPCEABI.bare.H::strcmp((char *)uVar4,s_playSE_8035f5fc);
if (iVar2 == 0) {
  uVar3 = createFunction(DAT_803607e8,pWVar1,playSE_,param_3);
}
else {
  iVar2 = MSL_C.PPCEABI.bare.H::strcmp((char *)uVar4,s_playBGM_8035f608);
  if (iVar2 == 0) {
    uVar3 = createFunction(DAT_803607e8,pWVar1,playBGM_,param_3);
  }
  else {
    uVar3 = 8;
  }
}
```
