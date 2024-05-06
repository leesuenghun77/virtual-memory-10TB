# virtual-memory-10TB
가상메모리 10TB 설정
#!/bin/bash

# 가상 메모리 파일 생성
dd if=/dev/zero of=virtual_memory.img bs=1 count=10TB status=progress

# 가상 메모리 파일을 loop 디바이스로 연결
losetup /dev/loop0 virtual_memory.img

# 가상 메모리를 스왑 파티션으로 설정
mkswap /dev/loop0
swapon /dev/loop0

echo "10TB 가상 메모리 생성 완료"


