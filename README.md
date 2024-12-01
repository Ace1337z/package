```git clone https://github.com/chanrio13/openwrt-ipq -b qualcommax-6.x-nss-wifi-6.9```

```cd openwrt-ipq```

```nano feeds.conf.default```
```
src-git nss_packages https://github.com/chanrio13/nss-packages.git;NSS-12.5-K6.x-wwan
src-git sqm_scripts_nss https://github.com/qosmio/sqm-scripts-nss.git
src-git passwall https://github.com/xiaorouji/openwrt-passwall.git
src-git passwall2 https://github.com/xiaorouji/openwrt-passwall2.git
src-git xray_core https://github.com/xiaorouji/Xray-core.git
src-git passpack https://github.com/xiaorouji/openwrt-passwall-packages.git
src-git cpufreq https://github.com/Ace1337z/openwrt-cpufreq.git
src-git atinout https://github.com/Ace1337z/luci-app-atinout-mod.git
src-git mihomo https://github.com/morytyann/OpenWrt-mihomo.git;main
src-git 3ginfolite https://github.com/4IceG/luci-app-3ginfo-lite.git
src-git modemband https://github.com/4IceG/luci-app-modemband.git
src-git sms https://github.com/4IceG/luci-app-sms-tool-js.git
```
```chmod +x feeds.conf.default```

```./scripts/feeds update && ./scripts/feeds install -a```

```cp nss-setup/config-nss.seed .config```

```make defconfig V=s```

```make download -j$(nproc) V=s```
```make -j$(nproc) V=maks```

