# AWS Generative AI PoC : Complex PDF RAG
#### for SC&T Trading

## 실행 환경
- Amazon SageMaker Studio - JupyterLab (Classic 아님)

## 주피터 노트북을 순서대로 실행하세요.
- 공통 : 01, 02 번 노트북은 환경설정 부분 입니다.
- Complex PDF RAG
  > 13 번 노트북은 OpenSearch에 PDF를 인덱싱 합니다.
  > 14 번 노트북은 RAG 기반 질의 응답을 합니다.
- Simple PDF RAG
  > 23 번 노트북은 PDF를 PDFPlumber로 파싱하여 인덱싱 하고, RAG 기반 질의 합니다. (Hybrid Search) <br>
  > 24 번 노트북은 PDF를 LLAMA-INDEX로 파싱하여 인덱싱 하고, RAG 기반 질의 합니다. (Hybrid Search)

![flow](./img/complex-pdf-workflow.png)

---

원본 소스는 아래 aws-samples git repo를 참조하세요.<br>
[RAG over Complex PDF on AWS](https://github.com/aws-samples/aws-ai-ml-workshop-kr/tree/c3d2185f419790905a2879284bf0c050355e0702/genai/aws-gen-ai-kr/20_applications/02_qa_chatbot/10_hands_on_lab/02_rag_over_complex_pdf)