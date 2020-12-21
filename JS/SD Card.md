# SD Card

You interact with this object using `wiiSDCard`.

There's no usable documentation here yet, but please take the following psuedocode:

```c
iVar2 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_checkValidSD_8030d26c);
if (iVar2 == 0) {
  uVar3 = createFunction(DAT_80360820,pWVar1,checkValidSD_,param_3);
}
else {
  iVar2 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_isInserted_8030d27c);
  if (iVar2 == 0) {
    uVar3 = createFunction(DAT_80360820,pWVar1,isInserted_,param_3);
  }
  else {
    iVar2 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_isJournaling_8030d288);
    if (iVar2 == 0) {
      uVar3 = createFunction(DAT_80360820,pWVar1,isJournaling_,param_3);
    }
    else {
      iVar2 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_getFreeKBytes_8030d298);
      if (iVar2 == 0) {
        uVar3 = createFunction(DAT_80360820,pWVar1,getFreeKBytes_,param_3);
      }
      else {
        iVar2 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_getSDBackupSize_8030d2a8);
        if (iVar2 == 0) {
          uVar3 = createFunction(DAT_80360820,pWVar1,getSDBackupSize_,param_3);
        }
        else {
          iVar2 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_setJournalFlag_8030d2b8);
          if (iVar2 == 0) {
            uVar3 = createFunction(DAT_80360820,pWVar1,setJournalFlag_,param_3);
          }
          else {
            iVar2 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_backupToSDCard_8030d2c8);
            if (iVar2 == 0) {
              uVar3 = createFunction(DAT_80360820,pWVar1,backupToSDCard,param_3);
            }
            else {
              iVar2 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_stopBackupToSDCard_8030d2d8);
              if (iVar2 == 0) {
                uVar3 = createFunction(DAT_80360820,pWVar1,stopBackupToSDCard_,param_3);
              }
              else {
                iVar2 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_setCancelJournal_8030d2ec);
                if (iVar2 == 0) {
                  uVar3 = createFunction(DAT_80360820,pWVar1,setCancelJournal_,param_3);
                }
                else {
                  iVar2 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_hasProgressFinished_8030d300);
                  if (iVar2 == 0) {
                    uVar3 = createFunction(DAT_80360820,pWVar1,hasProgressFinished_,param_3);
                  }
                  else {
                    uVar3 = 8;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
}

```
