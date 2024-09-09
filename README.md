# nx + expo + expo-router

https://github.com/nrwl/nx/discussions/21847?sort=old  

i followed these instructions:
https://github.com/nrwl/nx/issues/23101#issuecomment-2147308325  


<a alt="Nx logo" href="https://nx.dev" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/nrwl/nx/master/images/nx-logo.png" width="45"></a>

✨ **This workspace has been generated by [Nx, Smart Monorepos · Fast CI.](https://nx.dev)** ✨


## Pre-requisites

node v20.14.0  
npm v10.7.0  

## Setup

```bash
npm install
```

## Start the app

```bash
npx nx start mobile
```

## Creating dev builds

https://stackoverflow.com/questions/77367846/distribution-certificate-with-fingerprint-hasnt-been-imported-successfully

### install dev builds on simulators
https://chatgpt.com/share/d3718fe6-3797-44e8-a2fa-4a75690aaa04

nx build:ios:development-simulator mobile  
tar -xzf apps/mobile/build-1725475078413.tar.gz  
xcrun simctl install booted NXExpoRouter.app  
xcrun simctl launch booted com.yehonadavvibez.nxexporouter  

nx build:android:development mobile  
adb install apps/mobile/build-1725483613172.apk  
adb shell monkey -p com.yehonadavvibez.nxexporouter -c android.intent.category.LAUNCHER 1  


### install dev builds on real devices

nx build:android:development mobile  
adb install apps/mobile/build-1725483613172.apk

https://chatgpt.com/share/2982c720-d4f6-455c-9002-299adde8cd10  
nx build:ios:development mobile  
