# 딥러닝 수업 프로젝트: 이미지 컬러화

[![Python](https://img.shields.io/badge/python-3.10-3776AB?logo=python&logoColor=white)](https://www.python.org) [![License](https://img.shields.io/badge/license-Apache--2.0-blue.svg)](LICENSE)

국민대학교 딥러닝 수업에서 한국 음식 이미지 컬러화를 주제로 ChromaGAN·DeOldify·InstColorization 세 모델을 비교한 팀 프로젝트입니다. 컬러화 모델이 학습 도메인과 비슷한 이미지에서만 잘 동작하는 한계에서 출발해, 세 모델을 같은 한국 음식 데이터에 적용하고 진행 과정과 결과를 정성 비교로 정리했습니다.

## 개요

| 구분 | 내용 |
| --- | --- |
| 수업 | 국민대학교 딥러닝 |
| 기간 | 2022.09 – 2022.12 |
| 형태 | 팀 프로젝트 (3인) |
| 데이터 | AI Hub 한국 음식 이미지 (150종 × 1,000장) |
| 과제 | 흑백 이미지 컬러화 모델 비교와 fine-tuning |
| 평가 | 원본 컬러와의 정성 비교, PSNR·SSIM 지표 코드 |

## 접근

- AI Hub 한국 음식 이미지를 224×224 컬러/그레이 쌍으로 변환해 학습·평가 데이터를 만들었습니다. Colab 메모리 제약으로 train 12,922장·test 2,465장으로 줄여 사용했습니다.
- ChromaGAN은 PyTorch remake 구현을 가져와 한국 음식 이미지로 10 epoch fine-tuning했습니다(lr 2e-5, Colab Pro). 결과는 기존 weight 추론, 원본 컬러 이미지와 나란히 비교했습니다.
- DeOldify는 학습이 진행되지 않아 사전학습 모델로 테스트 그레이 이미지를 일괄 추론했습니다.
- InstColorization은 원저자의 사전학습 weight 배포 URL이 삭제되어 일부 checkpoint만 확보했고, fine-tuning이 중단된 지점까지를 노트북에 기록했습니다.
- 평가는 원본 컬러 이미지와의 정성 비교로 정리했고, PSNR·SSIM 계산 코드를 함께 남겼습니다.

## 저장소 구성

모델별 실행 노트북과 최종 발표 자료를 남겼습니다.

```text
.
├── notebooks/
│   ├── chroma_gan.ipynb                 # ChromaGAN을 한국 음식 이미지로 fine-tuning
│   ├── deoldify_inference.ipynb         # DeOldify 사전학습 모델로 일괄 추론
│   ├── instcolorization_training.ipynb  # InstColorization fine-tuning 시도 기록
│   └── psnr_ssim_eval.ipynb             # PSNR·SSIM 지표 코드
├── reports/
│   └── Deep-Learning-Project.pdf        # 최종 발표 자료 (모델 비교와 결과)
└── README.md
```

## 공개 범위

- ChromaGAN 노트북은 직접 작성했고, DeOldify·InstColorization 노트북은 각 공개 저장소의 Colab 노트북을 바탕으로 데이터 경로와 실행 설정을 수정한 것입니다. 모델 코드는 노트북에서 `git clone`으로 내려받습니다.
- AI Hub 원본 데이터와 학습 weight, 생성한 이미지는 포함하지 않았습니다. 세 모델의 비교 결과는 발표 자료에 정리했습니다.
- 노트북 출력과 코랩 드라이브 절대경로는 정리했습니다.

## 링크

- [AI Hub 한국 음식 이미지](https://www.aihub.or.kr/aihubdata/data/view.do?dataSetSn=79)
- [ChromaGAN (PyTorch remake)](https://github.com/superhighlevel/ChromaGan_Pytorch_Remake)
- [DeOldify](https://github.com/jantic/DeOldify)
- [InstColorization](https://github.com/ericsujw/InstColorization)

## 라이선스

Apache License 2.0. 자세한 내용은 [LICENSE](LICENSE)에 있습니다.
