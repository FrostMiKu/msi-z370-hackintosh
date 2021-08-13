# Credit and many thanks to [FrostMiKu](https://github.com/FrostMiKu/msi-z370-i5-9500-hackintosh)

从 specs 来看，[MSI Z370 OC GAMING](https://cn.msi.com/Motherboard/Z370-OC-GAMING/Specification)和[MSI Z370-A PRO](https://cn.msi.com/Motherboard/Z370-A-PRO/Specification)，几乎一致，只是前者比后者少了 VGA 接口。

我利用 FrostMiKu 的 EFI 进行 hackintosh，绝大多数功能都正常工作，但板载网卡无法工作，系统报告中 ethernet 显示为空，查看详细的 specs 发现使用的是**RTL8111H Gigabit 网卡**，利用 hackintool 下载该驱动，顺利解决。

疑问：Z370 OC GAMING 和 Z370-A PRO 的板载网卡都是**RTL8111H Gigabit 网卡**，为什么 FrostMiKu 那边板载网卡能正常工作？

---

该 EFI 与 FrostMiKu 的区别：

1. 添加了`RealtekRTL8111.kext`内核驱动
2. 设置`AllowNvramReset`为 true
3. 设置`HideAuxiliary`为 false (这个为 true 的话，即使`AllowNvramReset`为 true，引导界面不会出现清除 nvram 选项)

---

# msi-z370-i5-9500-hackintosh

msi z370 a pro、i5 9500、gtx1070ti 自用双系统 Win10/Mac 11.2 Big Sur（屏蔽独显）

MSI z370 oc gaming & i5 8600k 感谢 [@ShawLocke](https://github.com/ShawLocke) 帮助测试 [了解更多](https://github.com/FrostMiKu/msi-z370-i5-9500-hackintosh/issues/2)

## update

**更新前建议重置 NVRAM**

- 2021.8.12 测试支持 10.15.7

- 2021.2.11 支持 macOS 11.2 Big Sur , 添加 Opencore 启动 UI ,简化 EFI ,修改 UHD630 为桌面版 （除夕

- 2020.4.03 支持 10.15.4

## settings

型号已经选好，请自己生成 SMBIOS。

### WIFI/蓝牙

自用 BCM94360CD 免驱

- [x] ✅ handoff

- [x] ✅ airdorp

- [x] ✅ AirPods

- [x] ✅ 随航

## 驱动

- [x] ✅ uhd 630 驱动

- [x] ✅ 声卡驱动

- [x] ✅ 网卡驱动

- [x] ✅ 睡眠(非休眠)

https://blog.frostmiku.com/archives/28/
