# KidGuo NetEase client — OpenHarmony 4.1 port

Upstream: `kidGuo/HarmonyOS-NetEase-Cloud-Music` (source snapshot imported for porting).

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
