# Noised-Korean-Review-Deobfuscator

난독화된 한글 리뷰 복원 AI 경진대회 [데이콘 링크](https://dacon.io/competitions/official/236446/overview/description)

---

**읶겄돆 핶돆핶볶싞짂** 팀의 [beomi/gemma-ko-7b](https://huggingface.co/beomi/gemma-ko-7b) 파인튜닝 부분에 대한 코드입니다. <br/>
파인튜닝 부분은 GPU 사용 문제로 Colab이 아닌, 다음과 같은 Runpod 환경에서 별개로 실행되었습니다. <br/>

* OS: ubuntu22.04
* CPU: Intel(R) Xeon(R) Platinum 8462Y 16 Core CPU
* RAM: 251GB
* GPU: A100 SXM
* VRAM: 80GB
* py3.10, pytorch 2.2.0, cuda12.1.1

<br/>
기본 Volume Disk인 \workspace 내 디렉토리 구조는 다음과 같습니다. <br/>
<br/>

```python
[workspace]
 ┣━ data ------------------------------- # 파인튜닝을 하는데 필요한 훈련 및 추론 데이터
 ┃   ┣━ sample_submission.csv
 ┃   ┣━ finetuning_train_mlp.csv
 ┃   ┣━ finetuning_train_original.csv
 ┃   ┣━ finetuning_test_mlp.csv
 ┃   ┗━ finetuning_test_original.csv
 ┣━ huggingface ------------------------ # 베이스 모델이 저장되는 디렉토리 (empty)
 ┣━ results0221 ------------------------ # MLP 해독을 input으로한 파인튜닝 (empty)
 ┣━ results0225 ------------------------ # Original 데이터를 input으로한 파인튜닝 (empty)
 ┣━ kogemma_0222_raw.csv --------------- # 추론 결과 with MLP input
 ┣━ kogemma_0226_raw.csv --------------- # 추론 결과 with Original input
 ┣━ requirements.txt
 ┗━ main.ipynb
```
