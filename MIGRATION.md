# KidGuo NetEase client — OpenHarmony 4.1 port

Upstream: `kidGuo/HarmonyOS-NetEase-Cloud-Music` (source snapshot imported for porting).

> **状态（2026-11-23）**：本移植计划已废弃。SDK 11 / 设备固件（OpenHarmony 4.1.7.5）没有任何
> State Management V2 装饰器（`@ComponentV2/@Local/@Param/@Trace` 等 0 命中），全量移植等于重写
> 状态层；已改为新建小工程 `ohos-netease`（bundle `com.local.netease`，API 11 + V1 + 零三方依赖，
> 远端 `Yuanyuan669/ohos-netease-player`）。本仓仅作上游参考保留，勿再按下列 Work items 开工。

## Upstream status

- `targetSdkVersion` / `compatibleSdkVersion`: `6.0.0(20)`, `runtimeOS: HarmonyOS`
- 90 `.ets` files, ~179 KB source
- dependency: `@ohos/axios ^2.2.6`
- module uses `routerMap` and a backup extension

## Port target

- OpenHarmony 4.1 / API 11 (`runtimeOS: OpenHarmony`, hvigor 3.2.4)
- bundle: `com.local.netease` (planned)
- device: LHT16, 1080x2408

## Work items

1. Retarget `build-profile.json5` / `oh-package.json5` / hvigor config to API 11.
2. Remove or replace `routerMap`, backup extension, and API 20-only permissions.
3. Replace `@ohos/axios` dependency if it cannot resolve on the API 11 toolchain.
4. Fix ArkTS compile errors after SDK downgrade.
5. Reuse the signing/ACL flow from `OhMusic` for system permissions if needed.

## Licensing

The upstream repository has no license file; its README says learning-only and
non-commercial use. This repo's LICENSE was added separately; confirm redistribution
rights before publishing the upstream source.
