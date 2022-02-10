# iptime-wanmac-changeur
--------------------
좋은 의도에서든 나쁜 의도에서든 외부 IP를 변경해야 하는 경우가 있습니다. IPTIME 공유기를 사용하는 가정의 경우, WAN MAC에 따라 IP를 할당하는 것으로 추정되는 ISP의 정책에 따라 IPTIME 설정에서 MAC 주소를 간단히 바꾸어줌으로써 외부 IP를 변경할 수 있습니다. selenium을 통해 이 작업을 자동화하였습니다. 다음의 코드를 재활용하세요.
 
```
import iptime
Driver = iptime.IptimeDriver("root", "root", 10)
for i in range(1, 255):
    for j in range(1, 255):
        Driver.ChangerPartiellement([-1, -1, -1, -1, i, j]) # 각 MAC 주소 자리, -1은 변경하지 않음.
        #
        # foo...
        #
```
