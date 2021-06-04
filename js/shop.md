# Shop

Pardon the mess, we said. Make this documented.

```c
  iVar2 = strcmp(s1,sreturnToUpdate_8030c880);
  if (iVar2 == 0) {
createFunction(DAT_803607f0,pWVar1,returnToUpdate,param_3);
  }
  else {
iVar2 = strcmp(s1,srebootSystem_8030c890);
if (iVar2 == 0) {
  createFunction(DAT_803607f0,pWVar1,rebootSystem,param3);
}
else {
  iVar2 = strcmp(__s1,s_returnToMenu_8030c8a0);
  if (iVar2 == 0) {
createFunction(DAT_803607f0,pWVar1,returnToMenu,param3);
  }
  else {
iVar2 = strcmp(__s1,s_jumpToEULAViewer_8030c8b0);
if (iVar2 == 0) {
  createFunction(DAT_803607f0,pWVar1,jumpToEULAViewer,param3);
}
else {
  iVar2 = strcmp(__s1,s_jumpToManualChannel_8030c8c4);
  if (iVar2 == 0) {
createFunction(DAT_803607f0,pWVar1,jumpToManualChannel,param3);
  }
  else {
iVar2 = strcmp(__s1,s_retry_8035f648);
if (iVar2 == 0) {
  createFunction(DAT_803607f0,pWVar1,retry,param3);
}
else {
  iVar2 = strcmp(__s1,s_beginWaiting_8030c8d8);
  if (iVar2 == 0) {
createFunction(DAT_803607f0,pWVar1,beginW,param3);
  }
  else {
iVar2 = strcmp(__s1,s_endWaiting_8030c8e8);
if (iVar2 == 0) {
  createFunction(DAT_803607f0,pWVar1,endW,param3);
}
else {
  iVar2 = strcmp(__s1,s_setWallpaper_8030c8f4);
  if (iVar2 == 0) {
createFunction(DAT_803607f0,pWVar1,setWallpaper,param3);
  }
  else {
iVar2 = strcmp(s1,s_disableHRP_8030c904);
if (iVar2 == 0) {
  createFunction(DAT_803607f0,pWVar1,cpShopUrl,param_3);
}
else {
  iVar2 = strcmp(s1,s_enableHRP_8030c910);
  if (iVar2 == 0) {
createFunction(DAT_803607f0,pWVar1,enableHRP,param3);
  }
  else {
iVar2 = strcmp(__s1,s_error_8035f650);
if (iVar2 == 0) {
  createFunction(DAT_803607f0,pWVar1,error,param3);
}
else {
  iVar2 = strcmp(__s1,s_closeManual_8030c91c);
  if (iVar2 == 0) {
createFunction(DAT_803607f0,pWVar1,closeManual,param3);
  }
  else {
iVar2 = strcmp(s1,s_errMsg_8035f658);
if (iVar2 == 0) {
  uVar3 = getErrMsg();
  setStrings(uVar3,param_3);
}
else {
  iVar2 = strcmp(s1,s_errCode_8035f660);
  if (iVar2 == 0) {
setErrorCode(DAT_803607f4,param_3);
  }
  else {
iVar2 = strcmp(s1,s_title_8035f668);
if (iVar2 == 0) {
  setStrings(7,param_3);
}
else {
  iVar2 = strcmp(s1,s_retryBtn_8030c928);
  if (iVar2 == 0) {
setStrings(8,param_3);
  }
  else {
iVar2 = strcmp(s1,s_menuBtn_8035f670);
if (iVar2 == 0) {
  if ((DAT_80360728 == 2) || (DAT_80360728 == 8)) {
setStrings(0xc,param_3);
  }
  else {
setStrings(9,param_3);
  }
}
else {
  iVar2 = strcmp(s1,s_wiiUMenuBtn_8030c934);
  if (iVar2 == 0) {
setStrings(0xe,param_3);
  }
  else {
iVar2 = strcmp(s1,s_eulaBtn_8035f678);
if (iVar2 == 0) {
  setStrings(0xd,param_3);
}
else {
  iVar2 = strcmp(s1,s_eulaMsg_8035f680);
  if (iVar2 == 0) {
setStrings(5,param_3);
  }
  else {
iVar2 = strcmp(s1,s_manualChannelBtn_8030c940);
if (iVar2 == 0) {
  setStrings(0xf,param_3);
}
else {
  iVar2 = strcmp(s1,s_connecting_8030c954);
  if (iVar2 == 0) {

stopConnectionTimerQ33ipl10netconnect10NetConnectFv
  (DAT_8036c428);
setStrings(0x10,param_3);
  }
  else {
iVar2 = strcmp(s1,s_jumpDataMng_8030c960);
if (iVar2 == 0) {
  createFunction(DAT_803607f0,pWVar1,
 jumpDataManagement,param3);
}
else {
  iVar2 = strcmp(__s1,s_setSCARank_8030c96c);
  if (iVar2 == 0) {
createFunction(DAT_803607f0,pWVar1,setSCARank,
   param3);
  }
  else {
iVar2 = strcmp(s1,PTR_sa__8030c7c0);
if (iVar2 == 0) {
  zz_8002a9a0(0,param3);
}
else {
  iVar2 = strcmp(s1,PTR_sb__8030c7c4);
  if (iVar2 == 0) {
zz_8002a9a0(1,param3);
  }
  else {
iVar2 = strcmp(s1,PTR_sc__8030c7c8);
if (iVar2 == 0) {
  zz_8002a9a0(2,param3);
}
else {
  iVar2 = strcmp(s1,PTR_sd__8030c7cc);
  if (iVar2 == 0) {
zz_8002a9a0(3,param3);
  }
  else {
iVar2 = strcmp(__s1,
  s_isCompatibleMode_8030c978);
  if (iVar2 == 0) {
zz_8002a9d0((uint)DAT803607f9,param_3);
  }
  else {
iVar2 = strcmp(__s1,s_launchCode_8030c98c);
if (iVar2 == 0) {
  zz_8002a9d0(DAT_80360728 & 0xff,param_3);
```

