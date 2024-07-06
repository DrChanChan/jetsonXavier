# jetsonXavier
#초기 셋팅
1. https://makejarvis.tistory.com/88
   
# 쿨러 돌리기
jetson_clocks --fan


# opencv with cuda 설치
1. https://blog.naver.com/dldudcks1779/222197473350
2. https://velog.io/@jihyeon9975/openpose

#jetson xavier는 aarch로 Miniconda를 설치 권장함
1. 설치 후 miniconda 실행 : eval "$(/home/pyc/miniforge3/bin/conda shell.bash hook)"

# --apt-fix-broken 오류:
1.https://unix.stackexchange.com/questions/537546/e-unmet-dependencies-try-apt-fix-broken-install-with-no-packages-or-speci

#pytorch 설치 :
1. https://forums.developer.nvidia.com/t/pytorch-for-jetson/72048
2. OpenBLAS 설치 : sudo apt install libopenblas-dev
3. 테스트 코드 :
import torch
print("PyTorch version:", torch.__version__)
print("CUDA version:", torch.version.cuda)
print("Is CUDA available:", torch.cuda.is_available())

if torch.cuda.is_available():
    print("Number of GPUs:", torch.cuda.device_count())
    for i in range(torch.cuda.device_count()):
        print(f"GPU {i}: {torch.cuda.get_device_name(i)}")
else:
    print("CUDA is not available")
