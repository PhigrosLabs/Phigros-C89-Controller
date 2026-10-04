# 鏋勫缓涓庡彂甯?
## 绉佹湁浠撳簱鏈湴楠岃瘉

浣跨敤 Flutter 3.44.1 / Dart 3.12.1锛?
```sh
flutter pub get
flutter analyze
flutter test
flutter build apk --debug
```

Windows 闇€瑕?Visual Studio C++ 妗岄潰寮€鍙戝伐浣滆礋杞姐€丆Make 鍜屽搴斿伐鍏烽摼鐨?ATL锛涗笉寰楁彁浜ゆ湰鏈?SDK/澶存枃浠剁粷瀵硅矾寰勩€侺inux 瀹夎 GTK3銆乴ibsecret 寮€鍙戝寘銆侫ndroid 浣跨敤 JDK 17 涓?Flutter 瑕佹眰鐨?Android SDK銆侫pple 骞冲彴闇€ macOS/Xcode锛涚洰鍓嶄笉閰嶇疆 Apple 绛惧悕璇佷功銆?
## 鑷姩鏋勫缓

绉佹湁浠撳簱 push / pull_request / 鎵嬪姩杩愯瑙﹀彂 GitHub Actions銆傛祴璇曢€氳繃鍚庡垎鍒瀯寤?Android銆乄indows銆丩inux銆乵acOS銆乮OS锛涙櫘閫氭彁浜ょ敓鎴?Debug锛屽彂甯冩彁浜ょ敓鎴?Release锛屽苟浣跨敤 `--obfuscate --split-debug-info`銆傛贩娣嗕笉鏄繚瀵嗕繚璇侊紝涔熶笉鏄弽璋冭瘯瀹炵幇銆?
鏋勫缓浜х墿淇濆瓨鍦ㄧ鏈?Actions artifacts銆俙private-symbols-*` 浠呬緵缁存姢鑰呰繕鍘熷爢鏍堬紝涓嶄笂浼犲叕寮€浠撳簱銆傛闈笌 Apple 浜х墿鐢?tar.gz 淇濈暀鐩綍缁撴瀯鍜屾潈闄愶紱Android 鍙﹀鎻愪緵 APK銆傞粯璁?Android debug 绛惧悕涓嶉渶瑕佷笂浼?keystore锛屼絾涓嶅悓 runner 鐨勫瘑閽ュ彲鑳戒笉鍚屻€?
## 鍏紑鍙戝竷

鍒涘缓褰㈠ `v1.6.7` 鐨?Git tag锛屾垨鍦ㄦ彁浜や俊鎭腑浣跨敤锛?
```text
feat: 鍙戝竷鏂扮増鏈?
鏈鏇存柊璇存槑銆?[release ver="v1.6.7",pre=false,draft=false]
```

棣栬涓?Release 鏍囬锛屼綑涓嬪唴瀹瑰幓鎺夋爣璁板悗浣滀负姝ｆ枃銆傚甫鍚庣紑鐨?tag 榛樿棰勫彂甯冿紱鏍囪鍙樉寮忔寚瀹?pre/draft銆倀ag 涓庢爣璁板悓鏃跺瓨鍦ㄦ椂鐗堟湰蹇呴』鐩稿悓銆備笉瑕佸皢鍚屼竴鐗堟湰浠ュ垎鏀彁浜ゅ拰 tag 閲嶅瑙﹀彂鍙戝竷锛涘凡瀛樺湪鐨?Release 涓嶈嚜鍔ㄨ鐩栥€?
鍙戝竷浠诲姟浣跨敤 `public-release` 鐜銆傜淮鎶よ€呭簲閰嶇疆瀹℃壒浜轰笌浠呭彈淇′换鍒嗘敮/tag 鍙彂甯冪殑闄愬埗銆傚湪绉佹湁浠撳簱璁剧疆 `PUBLIC_RELEASE_TOKEN`锛氫娇鐢ㄤ粎鑳借闂叕寮€浠撳簱銆佸叿鏈?Contents write 鏉冮檺鐨?fine-grained PAT锛屾垨绛夋晥 GitHub App token銆傞粯璁?`GITHUB_TOKEN` 娌℃湁璺ㄤ粨搴撳彂甯冩潈闄愩€傛湰鏈?CLI 鐧诲綍鍑嵁涓嶅簲鐩存帴澶嶅埗涓?Actions secret銆?
鍏紑浠撳簱浠呬汉宸ュ悓姝ョ粡杩囧鏍哥殑 `README.md` 鍜?`docs/build-and-release.md`锛岀粷涓嶆帹閫佺鏈変粨搴撶殑 Git 鍘嗗彶銆乶otes銆佹簮鐮佹垨 symbols銆傚伐浣滄祦鍙皢 app-* 浜х墿涓婁紶鍏紑 Release銆?
iOS 杈撳嚭鏈鍚?.app锛屼笉鏄彲鐩存帴瀹夎鐨?IPA锛涢渶瑕佸紑鍙戣€呰嚜宸辩殑绛惧悕鍜屽垎鍙戞祦绋嬨€俶acOS 灏氭湭鍏瘉銆傚疄闄呬簯绔瀯寤轰笌骞冲彴瀹夎鎴愬姛鍓嶏紝涓嶅簲瀹ｅ竷姝ｅ紡鍙敤銆
