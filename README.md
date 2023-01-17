# Test with Quick Draw

## 1. [Anaconda 설치](https://docs.anaconda.com/anaconda/install/), [CUDA Toolkit 설치](https://developer.nvidia.com/cuda-11.0-download-archive?target_os=Windows&target_arch=x86_64&target_version=10&target_type=exenetwork)

<br>

* 시스템 변수 - path에 환경 변수도 추가해주자.

<img width="342" alt="image" src="https://user-images.githubusercontent.com/75800620/212959520-eee62548-a62b-4ca2-b30d-286116fe485f.png">

<br>

## 2. 가상 환경 생성

```
conda create -n 가상환경이름 python=3.6  // python 버전 3.6으로 설치
conda env list  // 가상환경 목록
(conda) activate 가상환경이름  // 실행
(conda) deactive 가상환경이름  // 종료

/*
conda create -n tftest python=3.6
conda activate tftest
*/
```

<br>

## 3. 패키지 설치

```
pip install tensorflow
pip install matplotlib
pip install opencv-python==4.5.5.64
pip install keras
pip install pandas
pip install sklearn
pip install scikit-learn
pip install scipy
```

<br>

## 4. 주피터 노트북에 가상환경 등록

```
pip install jupyter notebook
python -m ipykernel install --user --name 가상환경이름 --display-name "표시할 커널이름"  // 커널 연결

// python -m ipykernel install --user --name tftest --display-name "tftest"

jupyter notebook  // 주피터 노트북 실행
```

<br>

## 5. 데이터 구성

a. clone 받은 폴더 안에 data 폴더 만들기  
b. [데이터셋](https://console.cloud.google.com/storage/browser/quickdraw_dataset/full/numpy_bitmap;tab=objects?prefix=&forceOnObjectsSortingFiltering=false)에서 학습시키고자 하는 .npy 파일들을 ```/data```폴더 안에 넣기

<br>

## 6. 실행

### a. ```jupyter notebook```으로 실행된 jupyter notebook에서 ```QuickDrawTest.ipynb``` 파일을 연 후 실행시킨다.

<br>

![image](https://user-images.githubusercontent.com/75800620/212951112-7a29f419-8337-42a2-b040-d3221aa7be44.png)

<br>


### b. clone 받은 폴더에 생성된 ```class_names.txt```를 생성된 ```model``` 폴더 안으로 복사한다.

<br>

> ```model``` 폴더 안의 ```class_names.txt``` 내용의 파일 이름들을 간단하게 바꿔주면 결과를 직관적으로 볼 수 있다!

<br>

Ex)

### 수정 전 ```class_names.txt``` 파일 내용

```
full_numpy_bitmap_apple
full_numpy_bitmap_axe
full_numpy_bitmap_banana
full_numpy_bitmap_baseball bat
full_numpy_bitmap_bee
full_numpy_bitmap_book
```

### 수정 후 ```class_names.txt``` 파일 내용

```
apple
axe
banana
baseball bat
bee
book
```

<br>

### c. VSCode 등의 에디터로 ```index.html```을 서버에서 실행한다.

<br>

### d. 왼쪽 캔버스에 그림을 그려 정확도를 확인해볼 수 있다.

* 캔버스 하단 바를 조절해 그리는 선 굵기를 조절할 수 있다.

<br>

<img width="875" alt="image" src="https://user-images.githubusercontent.com/75800620/212957895-f3fc1a14-4a7f-4de2-984f-8cedda5ba06e.png">
