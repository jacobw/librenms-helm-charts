# Changelog

## [11.0.0](https://github.com/jacobw/librenms-helm-charts/compare/librenms-10.1.2...librenms-11.0.0) (2026-09-19)


### ⚠ BREAKING CHANGES

* `spec.selector` is immutable on Deployments and StatefulSets, so upgrading an existing release fails with `field is immutable`. Delete the librenms Deployments and the poller StatefulSet before upgrading. The PersistentVolumeClaims are separate objects and are not affected.
* Helm refuses to install or upgrade the chart on Kubernetes older than 1.26.

### Features

* add default values and adjust schema ([84b49a5](https://github.com/jacobw/librenms-helm-charts/commit/84b49a584fe83937e955a1050b7ef4e7d524eda1))
* add liveness probes and SNMP scanner job policy ([#271](https://github.com/jacobw/librenms-helm-charts/issues/271)) ([eb0a35e](https://github.com/jacobw/librenms-helm-charts/commit/eb0a35e168077d254743efcdfc13335b0f24c803))
* add nodeSelector support for SNMP scanner pods ([ce1d9c0](https://github.com/jacobw/librenms-helm-charts/commit/ce1d9c0c10b0f3500cb1482786ebfe162d7bb03f))
* add persistent storage configuration for frontend APP_KEY persistence ([407b82c](https://github.com/jacobw/librenms-helm-charts/commit/407b82ca80d1e4e7ca77a56b9e3336fa96ce4536))
* add securityContext to templates ([8d2a4d8](https://github.com/jacobw/librenms-helm-charts/commit/8d2a4d8fa709611a482d61448eee0d76e6a1e5d6))
* add snmptrapd sidecar support ([0786b70](https://github.com/jacobw/librenms-helm-charts/commit/0786b7022c9d3115fc2c45e5e3b3ef8a263c2b52))
* add snmptrapd sidecar support ([d1f1fc5](https://github.com/jacobw/librenms-helm-charts/commit/d1f1fc5d067df4d81dd59fe2e1172c19b3cad2fe))
* add support for extra envFrom sources in LibreNMS components ([86c2b9e](https://github.com/jacobw/librenms-helm-charts/commit/86c2b9e4c574a209cc126345130d64b7142aef07))
* add support for other pullPolicy ([39ac183](https://github.com/jacobw/librenms-helm-charts/commit/39ac18342b5013b19b29628aeeef431c9a0c8ad7))
* add values.schema.json for LibreNMS Helm Chart configuration ([583c04e](https://github.com/jacobw/librenms-helm-charts/commit/583c04e7dcb3b6eb769ce8ad1f372110bdf94e72))
* follow the standard Kubernetes label conventions ([#269](https://github.com/jacobw/librenms-helm-charts/issues/269)) ([dc852b1](https://github.com/jacobw/librenms-helm-charts/commit/dc852b1943f5fdc424faf186e0b5439fa6257a04))
* **frontend:** add appUrl and appTrustedProxies for ingress TLS termination ([f26a91e](https://github.com/jacobw/librenms-helm-charts/commit/f26a91eaa36362892e4c3ae770f41539d4c1db99))
* **frontend:** add appUrl and appTrustedProxies for ingress TLS termination ([6cddad8](https://github.com/jacobw/librenms-helm-charts/commit/6cddad8113222c965a21daa66fd784a30c0b1844))
* **frontend:** gate readiness on the LibreNMS health endpoint ([#272](https://github.com/jacobw/librenms-helm-charts/issues/272)) ([2cd87d5](https://github.com/jacobw/librenms-helm-charts/commit/2cd87d556db57294d339763a7e6f12a0010523aa))
* **gateway:** add Gateway API HTTPRoute for the frontend ([d1eaf9a](https://github.com/jacobw/librenms-helm-charts/commit/d1eaf9afdb1cf6aaed4b267ae505ef576d5adf72))
* **gateway:** add Gateway API HTTPRoute for the frontend ([f64dce3](https://github.com/jacobw/librenms-helm-charts/commit/f64dce3ed2444d1299c870fd00e01a9326db8574))
* **mysql:** replace Bitnami MySQL with HelmForge MySQL ([ce1f06e](https://github.com/jacobw/librenms-helm-charts/commit/ce1f06eaaddbbf8efa3f26410626cae20f3343ab))
* replace database.mode with externalDatabase and mysql.enabled toggle ([9c9c5fb](https://github.com/jacobw/librenms-helm-charts/commit/9c9c5fbd121c04a9e97b362925eb75372ab8bc76))
* require Kubernetes 1.26 or newer ([#265](https://github.com/jacobw/librenms-helm-charts/issues/265)) ([d82004d](https://github.com/jacobw/librenms-helm-charts/commit/d82004d7981c156c16186a0d174b85c3dcde0d08))
* **syslogng:** expose service type and traffic policy to preserve source IP ([8340500](https://github.com/jacobw/librenms-helm-charts/commit/834050001027bb18b312d4f075141ecb186037d3))
* **syslogng:** expose service type and traffic policy to preserve source IP ([c94f198](https://github.com/jacobw/librenms-helm-charts/commit/c94f198ece4b1df89fef54ac971c700afc6febd6))
* update values and schema ([9e6e504](https://github.com/jacobw/librenms-helm-charts/commit/9e6e504fcd682e8b87b0842ac3472dab33f5200d))
* use native LibreNMS APP_KEY generation ([1814812](https://github.com/jacobw/librenms-helm-charts/commit/1814812a499515123641a78befe1599e12703dd1))


### Bug Fixes

* 151 replace bitnami redis helmchart ([9d32902](https://github.com/jacobw/librenms-helm-charts/commit/9d329024203187fe94921d992743e85a12094b89))
* adjust indentation for extra environment variables in librenms-cron.yml ([06a5f58](https://github.com/jacobw/librenms-helm-charts/commit/06a5f58775075a9465cba12ebfd1cea55962218b))
* appkey generation ([6f5beef](https://github.com/jacobw/librenms-helm-charts/commit/6f5beefcbe6e42102ca88e25cb2cf070a00083f6))
* **configmap:** gate Redis and RRDCached settings on their toggles ([11121f8](https://github.com/jacobw/librenms-helm-charts/commit/11121f873ecb05f166a529256bc376dfa719fede))
* **configmap:** gate Redis and RRDCached settings on their toggles ([420603c](https://github.com/jacobw/librenms-helm-charts/commit/420603c282ed57fa9e2f65d24f9e7df8d4d71ca4))
* extra environment variables in LibreNMS components ([0f1c403](https://github.com/jacobw/librenms-helm-charts/commit/0f1c4033478d2e916e30a57c8b7e0724b268b78a))
* **ingress:** stop mutating global values, refresh the annotations example ([2a42127](https://github.com/jacobw/librenms-helm-charts/commit/2a421275db22026c274588a68a837409fadd2ca9))
* **ingress:** stop mutating global values, refresh the annotations example ([eca257c](https://github.com/jacobw/librenms-helm-charts/commit/eca257c195da6ce5b16a60a1161731dddda4944d))
* **mysql:** disable binary logging by default ([6ba49f0](https://github.com/jacobw/librenms-helm-charts/commit/6ba49f08c1bcd9b4a12df38cb75613628d7fa2c0))
* **mysql:** disable binary logging by default ([15e1b58](https://github.com/jacobw/librenms-helm-charts/commit/15e1b5869a3c142c23b734c97136defc25f40945)), closes [#178](https://github.com/jacobw/librenms-helm-charts/issues/178)
* resource indentation in template files ([869e37e](https://github.com/jacobw/librenms-helm-charts/commit/869e37e226fbd117350fb5e126ac3c3443d71006))
* **secret:** preserve the generated APP_KEY across upgrades ([4560bfb](https://github.com/jacobw/librenms-helm-charts/commit/4560bfbe4dd3e9c43997a04762d284c477a7993a))
* **secret:** preserve the generated APP_KEY across upgrades ([dcaa088](https://github.com/jacobw/librenms-helm-charts/commit/dcaa0885876b4aa9e70ab724d36499c185152363))
* **serviceaccount:** make serviceAccountName settable, drop dead helpers ([50e25e7](https://github.com/jacobw/librenms-helm-charts/commit/50e25e76cb2225957569bdcadba1719457605e4a))
* **serviceaccount:** make serviceAccountName settable, drop dead helpers ([8aefe00](https://github.com/jacobw/librenms-helm-charts/commit/8aefe005a4c338170c47dace429ec15bd8205791))
* spacing ([d2afc8c](https://github.com/jacobw/librenms-helm-charts/commit/d2afc8c57865c6ea51d40423a849c71f32840df0))
* typos in values, readme and schema ([09878cf](https://github.com/jacobw/librenms-helm-charts/commit/09878cf47326c1cb1050ad7dedec1357d41197ec))
* update init container image tag format in values.yaml ([6e4a43b](https://github.com/jacobw/librenms-helm-charts/commit/6e4a43b12a24f298019bc467f9cffcccecc05099))
* update librenms/librenms docker tag to v26.8.2 ([#277](https://github.com/jacobw/librenms-helm-charts/issues/277)) ([42dac23](https://github.com/jacobw/librenms-helm-charts/commit/42dac23e2e23bb4afebed0c8ba7d83f9f978ace1))


### Dependencies

* update helm release redis to v3 ([#283](https://github.com/jacobw/librenms-helm-charts/issues/283)) ([222a0e4](https://github.com/jacobw/librenms-helm-charts/commit/222a0e492d722346402b80830a07b2f86a3dbb5c))

## [10.1.2](https://github.com/librenms/helm-charts/compare/librenms-10.1.1...librenms-10.1.2) (2026-09-18)


### Dependencies

* update helm release redis to v3 ([#283](https://github.com/librenms/helm-charts/issues/283)) ([222a0e4](https://github.com/librenms/helm-charts/commit/222a0e492d722346402b80830a07b2f86a3dbb5c))

## [10.1.1](https://github.com/librenms/helm-charts/compare/librenms-10.1.0...librenms-10.1.1) (2026-09-01)


### Bug Fixes

* update librenms/librenms docker tag to v26.8.2 ([#277](https://github.com/librenms/helm-charts/issues/277)) ([42dac23](https://github.com/librenms/helm-charts/commit/42dac23e2e23bb4afebed0c8ba7d83f9f978ace1))

## [10.1.0](https://github.com/librenms/helm-charts/compare/librenms-10.0.0...librenms-10.1.0) (2026-08-28)


### Features

* add liveness probes and SNMP scanner job policy ([#271](https://github.com/librenms/helm-charts/issues/271)) ([eb0a35e](https://github.com/librenms/helm-charts/commit/eb0a35e168077d254743efcdfc13335b0f24c803))
* **frontend:** gate readiness on the LibreNMS health endpoint ([#272](https://github.com/librenms/helm-charts/issues/272)) ([2cd87d5](https://github.com/librenms/helm-charts/commit/2cd87d556db57294d339763a7e6f12a0010523aa))

## [10.0.0](https://github.com/librenms/helm-charts/compare/librenms-9.2.1...librenms-10.0.0) (2026-08-28)


### ⚠ BREAKING CHANGES

* `spec.selector` is immutable on Deployments and StatefulSets, so upgrading an existing release fails with `field is immutable`. Delete the librenms Deployments and the poller StatefulSet before upgrading. The PersistentVolumeClaims are separate objects and are not affected.
* Helm refuses to install or upgrade the chart on Kubernetes older than 1.26.

### Features

* follow the standard Kubernetes label conventions ([#269](https://github.com/librenms/helm-charts/issues/269)) ([dc852b1](https://github.com/librenms/helm-charts/commit/dc852b1943f5fdc424faf186e0b5439fa6257a04))
* require Kubernetes 1.26 or newer ([#265](https://github.com/librenms/helm-charts/issues/265)) ([d82004d](https://github.com/librenms/helm-charts/commit/d82004d7981c156c16186a0d174b85c3dcde0d08))

## [9.2.1](https://github.com/librenms/helm-charts/compare/librenms-9.2.0...librenms-9.2.1) (2026-08-28)


### Bug Fixes

* **configmap:** gate Redis and RRDCached settings on their toggles ([420603c](https://github.com/librenms/helm-charts/commit/420603c282ed57fa9e2f65d24f9e7df8d4d71ca4))
* **ingress:** stop mutating global values, refresh the annotations example ([eca257c](https://github.com/librenms/helm-charts/commit/eca257c195da6ce5b16a60a1161731dddda4944d))
* **secret:** preserve the generated APP_KEY across upgrades ([dcaa088](https://github.com/librenms/helm-charts/commit/dcaa0885876b4aa9e70ab724d36499c185152363))
* **serviceaccount:** make serviceAccountName settable, drop dead helpers ([8aefe00](https://github.com/librenms/helm-charts/commit/8aefe005a4c338170c47dace429ec15bd8205791))
