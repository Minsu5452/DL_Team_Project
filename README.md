# 딥러닝 수업 프로젝트: 이미지 컬러화

[![Python](https://img.shields.io/badge/python-3.10-3776AB?logo=python&logoColor=white)](https://www.python.org) [![License](https://img.shields.io/badge/license-Apache--2.0-blue.svg)](LICENSE)

국민대학교 딥러닝 수업에서 한국 음식 이미지 컬러화를 주제로 ChromaGAN·DeOldify·InstColorization 세 모델을 비교한 팀 프로젝트입니다. 흑백 이미지에 색을 입히는 여러 접근을 같은 도메인 데이터로 비교하고, PSNR·SSIM과 정성 평가로 결과를 정리했습니다.

## 개요

| 항목 | 내용 |
| --- | --- |
| 수업 | 국민대학교 딥러닝 |
| 기간 | 2022.09 – 2022.12 |
| 형태 | 팀 프로젝트 (3인) |
| 데이터 | AI Hub 한국 음식 이미지 |
| 과제 | 흑백 이미지 컬러화 모델 비교와 fine-tuning |
| 평가 | PSNR, SSIM, 정성 비교 |

## 접근

- AI Hub 한국 음식 이미지를 컬러/그레이 페어로 변환해 학습·평가 데이터를 만들었습니다.
- ChromaGAN(PyTorch remake)을 한국 음식 이미지로 fine-tuning하고, 기존 weight와 결과를 비교했습니다.
- DeOldify는 사전학습 모델로 추론하고, InstColorization은 재현 과정의 제약을 함께 기록했습니다.
- 세 모델의 결과를 PSNR·SSIM과 정성 비교로 평가했습니다.

## 저장소 구성

직접 작성한 ChromaGAN 노트북과 최종 발표 자료를 남겼습니다.

```text
.
├── notebooks/
│   ├── chroma_gan.ipynb          # ChromaGAN을 한국 음식 이미지로 fine-tuning
│   └── Chroma_gan_example.ipynb  # ChromaGAN 추론 예시
├── reports/
│   └── Deep-Learning-Project.pdf  # 최종 발표 자료 (모델 비교와 결과)
└── README.md
```

## 공개 범위

- 직접 작성한 코드는 ChromaGAN 노트북이고, DeOldify·InstColorization은 공개 저장소를 가져와 비교에 사용해 코드는 포함하지 않았습니다. 노트북에서는 필요한 저장소를 `git clone`으로 내려받습니다.
- AI Hub 원본 데이터와 학습 weight, 생성한 이미지는 포함하지 않았습니다. 세 모델의 비교 결과는 발표 자료에 정리했습니다.
- 노트북 출력과 코랩 드라이브 절대경로는 정리했습니다.

## 링크

- [AI Hub 한국 음식 이미지](https://www.aihub.or.kr/aihubdata/data/view.do?dataSetSn=79)
- [ChromaGAN (PyTorch remake)](https://github.com/superhighlevel/ChromaGan_Pytorch_Remake)
- [DeOldify](https://github.com/jantic/DeOldify)
- [InstColorization](https://github.com/ericsujw/InstColorization)

## 라이선스

Apache License 2.0. 자세한 내용은 [LICENSE](LICENSE)에 있습니다.
