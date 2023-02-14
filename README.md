# apple-preference-keys
Preference keys relating to core apple services ex SpringBoard / Carousel etc

doesn't contain everything

Carousel.framework (watchOS 8.5)

```

CSLSnapshotSystemInterval
CSLSnapshotInterval
JetsamBandManagerMaximumMemoryUsage
JetsamBandManagerMinimumFreeMemoryForElevation
SBLowBatteryLevel / SBHideACPower (yes, this is in watchOS, used in IOSSHLBatteryStatus)
CSLSoftwakeInterval (CSLSoftWakeScheduler)
CSLSoftwakeMaxBrightness (CSLSoftWakeScheduler)
CSLSoftwakeDebug (CSLSoftWakeScheduler)
CSLDisableSoftwake (CSLSoftWakeScheduler)
CSLInitialBrightness (CSLSoftWakeScheduler)


CSLDisableDetents (CSLDetentManager)
CSLDebugDetents (CSLDetentManager)

//remember to add functions and the classes the preferences are used in above latr

CSLDegreesPerDetent(_CSLLoadUnsignedIntegerPreference(@"CSLDegreesPerDetent", 0x12);, CSLDetentManager)

IntervalBetweenSnapshots (_CSLLoadTimeIntervalPreference(@"IntervalBetweenSnapshots");, CSLSnapshotService)
CSLReturnToPrimaryUIInterval (_CSLLoadTimeIntervalPreference(@"CSLReturnToPrimaryUIInterval");, CSLSnapshotService)
CSLReturnToPrimaryUILeeway (_CSLLoadTimeIntervalPreference(@"CSLReturnToPrimaryUILeeway");, CSLSnapshotService)

CSLFlashDetents (_CSLLoadBooleanPreference(@"CSLFlashDetents", 0x0);, CSLDetentManager)
CSLDegreesPerDetent (_CSLLoadUnsignedIntegerPreference(@"CSLDegreesPerDetent", 0x12);, CSLDetentManager)

CSLAlwaysDetectOrientation (_CSLLoadBooleanPreference(@"CSLAlwaysDetectOrientation", 0x0);, CSLChargingManager)
MaxBudgetedComplications (_CSLLoadUnsignedIntegerPreference(@"MaxBudgetedComplications", [CSLDuetBudgetController budgetDefaultMaxComplicationApps]);, CSLComplicationMonitor)
com.apple.carousel.legacy-charging-status (????? weird name for a pref but this is the arg the function uses so ig it's this) (_CSLLoadBooleanPreference(@"com.apple.carousel.legacy-charging-status", 0x0), CSLStatusBarContext)
DisableActivateOnSettle (_CSLLoadBooleanPreference(@"DisableActivateOnSettle", *(int8_t *)___disableActivateOnSettle & 0xff);, CSLAppSwitcherDisplaySessionSettledState

irregular preferences in CSLWakeGestureManager that don't use csl preference functions but instead [NSUserDefaults standardUserDefaults] boolForKey: kDisallowWakeGestureSetting kDynamicWakeGestureSetting kDisallowSleepGestureSetting
nsuserdefault prefs in CSLSessionManager: (all boolForKey as well) mediaAutoLaunch phoneAutoLaunch WorkoutSportWatchMode
```
