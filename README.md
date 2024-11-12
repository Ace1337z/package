git clone https://github.com/chanrio13/openwrt-ipq -b qualcommax-6.x-nss-wifi
cd openwrt-ipq

nano feeds.conf.default

src-git packages https://github.com/immortalwrt/packages.git
src-git luci https://github.com/immortalwrt/luci.git
src-git routing https://git.openwrt.org/feed/routing.git
src-git telephony https://git.openwrt.org/feed/telephony.git
src-git nss_packages https://github.com/chanrio13/nss-packages.git;NSS-12.5-K6.x-wwan
src-git sqm_scripts_nss https://github.com/qosmio/sqm-scripts-nss.git
src-git passwall https://github.com/xiaorouji/openwrt-passwall.git
#src-git video https://github.com/openwrt/video.git
#src-git targets https://github.com/openwrt/targets.git
#src-git oldpackages http://git.openwrt.org/packages.git
#src-link custom /usr/src/openwrt/custom-feed

chmod +x feeds.conf.default

./scripts/feeds update
./scripts/feeds install -a

cp nss-setup/config-nss.seed .config

make defconfig V=s

make download -j$(nproc) V=s
make -j$(nproc) V=maks




src-git argon https://github.com/jerrykuku/luci-theme-argon.git

chmod -R u+w ./feeds

git clone https://github.com/jerrykuku/luci-theme-argon.git package/luci-theme-argon
