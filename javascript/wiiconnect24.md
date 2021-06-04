# WiiConnect24

You interact with this object using `wiiNwc24`.

There are both functions and getters not yet documented:

```c
iVar3 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_getFriendNum_8030cb94);
if (iVar3 == 0) {
  createFunction(DAT_80360808,pWVar2,getFriendNum_,param_3);
  goto LAB_8002c488;
}
iVar3 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_getFriendInfo_8030cba4);
if (iVar3 == 0) {
  createFunction(DAT_80360808,pWVar2,getFriendInfo_,param_3);
  goto LAB_8002c488;
}
iVar3 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_sendGiftMailAsync_8030cbb4);
if (iVar3 == 0) {
  createFunction(DAT_80360808,pWVar2,sendGiftMailAsync_,param_3);
  goto LAB_8002c488;
}
iVar3 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_sendReturnMailAsync_8030cbc8);
if (iVar3 == 0) {
  createFunction(DAT_80360808,pWVar2,sendReturnMailAsync_,param_3);
  goto LAB_8002c488;
}
iVar3 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_sendNormalMailAsync_8030cbdc);
if (iVar3 == 0) {
  createFunction(DAT_80360808,pWVar2,sendNormalMailAsync_,param_3);
  goto LAB_8002c488;
}
iVar3 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_isBusy_8035f69c);
if (iVar3 == 0) {
  createFunction(DAT_80360808,pWVar2,isBusy_,param_3);
  goto LAB_8002c488;
}
iVar3 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_dispError_8030cbf0);
if (iVar3 == 0) {
  createFunction(DAT_80360808,pWVar2,dispError_,param_3);
  goto LAB_8002c488;
}
iVar3 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_doLeftBtn_8030cbfc);
if (iVar3 == 0) {
  createFunction(DAT_80360808,pWVar2,doLeftBtn_,param_3);
  goto LAB_8002c488;
}
iVar3 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_doRightBtn_8030cc08);
if (iVar3 == 0) {
  createFunction(DAT_80360808,pWVar2,doRightBtn_,param_3);
  goto LAB_8002c488;
}
iVar3 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_myUserId_8030cc14);
if (iVar3 == 0) {
  *(undefined4 *)param_3 = 1;
  pvVar4 = ipl::System::getNwc24Manager();
  *(int *)((int)param_3 + 8) = (int)pvVar4 + 0x20;
  goto LAB_8002c488;
}
iVar3 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_mailErrNo_8030cc20);
if ((iVar3 == 0) || (iVar3 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_errCode_8035f6a8), iVar3 == 0)) {
  *(undefined4 *)param_3 = 2;
  getMiiManager__Q23ipl6SystemFv();
  uVar5 = RFLGetAsyncStatus();
  uVar1 = countLeadingZeros(uVar5);
  if (uVar1 >> 5 == 0) {
    getMiiManager__Q23ipl6SystemFv();
    iVar3 = RFLGetAsyncStatus();
    uVar1 = countLeadingZeros(&DAT_fffffff4 + iVar3);
    if (uVar1 >> 5 == 0) {
      *(double *)((int)param_3 + 8) = DOUBLE_80361670;
      goto LAB_8002c488;
    }
  }
  *(double *)((int)param_3 + 8) =
       (double)CONCAT44(0x43300000,DAT_80360800 ^ 0x80000000) - DOUBLE_80361678;
  goto LAB_8002c488;
}
iVar3 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_errCodeWithLabel_8030cc2c);
if (iVar3 == 0) {
  getMiiManager__Q23ipl6SystemFv();
  uVar5 = RFLGetAsyncStatus();
  uVar1 = countLeadingZeros(uVar5);
  uVar6 = DAT_80360800;
  if (uVar1 >> 5 == 0) {
    getMiiManager__Q23ipl6SystemFv();
    iVar3 = RFLGetAsyncStatus();
    uVar1 = countLeadingZeros(&DAT_fffffff4 + iVar3);
    uVar6 = DAT_80360800;
    if (uVar1 >> 5 == 0) {
      uVar6 = 109999;
    }
  }
  setErrorCode(uVar6,param_3);
  goto LAB_8002c488;
}
iVar3 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_errMsg_8035f6b0);
if (iVar3 == 0) {
  getMiiManager__Q23ipl6SystemFv();
  uVar5 = RFLGetAsyncStatus();
  uVar1 = countLeadingZeros(uVar5);
  if (uVar1 >> 5 == 0) {
    getMiiManager__Q23ipl6SystemFv();
    iVar3 = RFLGetAsyncStatus();
    uVar1 = countLeadingZeros(&DAT_fffffff4 + iVar3);
    if (uVar1 >> 5 == 0) {
      getMiiManager__Q23ipl6SystemFv();
      iVar3 = RFLGetAsyncStatus();
      uVar1 = countLeadingZeros(iVar3 + -3);
      if (uVar1 >> 5 == 0) {
        setStrings(0x1a,param_3);
      }
      else {
        setStrings(0x1d,param_3);
      }
      goto LAB_8002c488;
    }
  }
  if (DAT_80360804 == 0) {
    *(undefined4 *)param_3 = 1;
    *(code **)((int)param_3 + 8) = WWWAddJSPlugin;
  }
  else {
    uVar6 = convErrToMsgId__Q23ipl16shopNwc24ManagerFQ23EGG10Nwc24Errori
                      (DAT_80360804,DAT_80360800);
    setStrings(uVar6,param_3);
  }
  goto LAB_8002c488;
}
iVar3 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_ready_8035f6b8);
if (iVar3 == 0) {
  *(undefined4 *)param_3 = 3;
  uVar1 = countLeadingZeros(DAT_80360804);
  *(uint *)((int)param_3 + 8) = uVar1 >> 5;
  goto LAB_8002c488;
}
iVar3 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_sendable_8030cc40);
if (iVar3 == 0) {
  uVar5 = 0;
  if ((DAT_80360804 - 7U < 2) || (DAT_80360804 == 0)) {
    getMiiManager__Q23ipl6SystemFv();
    uVar7 = RFLGetAsyncStatus();
    uVar1 = countLeadingZeros(uVar7);
    if (uVar1 >> 5 != 0) {
      uVar5 = 1;
    }
  }
  *(undefined4 *)param_3 = 3;
  *(undefined4 *)((int)param_3 + 8) = uVar5;
  goto LAB_8002c488;
}
iVar8 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_leftBtn_8035f6c0);
iVar3 = DAT_80360804;
if (iVar8 != 0) {
  iVar8 = MSL_C.PPCEABI.bare.H::strcmp(__s1,s_rightBtn_8030cc4c);
  iVar3 = DAT_80360804;
  if (iVar8 != 0) goto LAB_8002c488;
  getMiiManager__Q23ipl6SystemFv();
  uVar5 = RFLGetAsyncStatus();
  uVar1 = countLeadingZeros(uVar5);
  if (uVar1 >> 5 == 0) {
    getMiiManager__Q23ipl6SystemFv();
    iVar8 = RFLGetAsyncStatus();
    uVar1 = countLeadingZeros(&DAT_fffffff4 + iVar8);
    if (uVar1 >> 5 != 0) goto LAB_8002c454;
    uVar6 = 10;
  }
  else {
LAB_8002c454:
    if ((iVar3 == 4) || (iVar3 == 0xc)) {
      uVar6 = 0xb;
    }
    else {
      uVar6 = 10;
    }
  }
  setStrings(uVar6,param_3);
  goto LAB_8002c488;
}
getMiiManager__Q23ipl6SystemFv();
uVar5 = RFLGetAsyncStatus();
uVar1 = countLeadingZeros(uVar5);
if (uVar1 >> 5 == 0) {
  getMiiManager__Q23ipl6SystemFv();
  iVar8 = RFLGetAsyncStatus();
  uVar1 = countLeadingZeros(&DAT_fffffff4 + iVar8);
  if (uVar1 >> 5 != 0) goto LAB_8002c39c;
  iVar3 = shop::GetLaunchCode();
  if ((iVar3 == 2) || (iVar3 = shop::GetLaunchCode(), iVar3 == 8)) {
    uVar6 = 0xc;
  }
  else {
    uVar6 = 9;
  }
}
else {
LAB_8002c39c:
  if ((iVar3 - 7U < 2) || (iVar3 == 10)) {
    uVar6 = 8;
  }
  else {
    iVar3 = shop::GetLaunchCode();
    if ((iVar3 == 2) || (iVar3 = shop::GetLaunchCode(), iVar3 == 8)) {
      uVar6 = 0xc;
    }
    else {
      uVar6 = 9;
    }
  }
}
setStrings(uVar6,param_3);
```

