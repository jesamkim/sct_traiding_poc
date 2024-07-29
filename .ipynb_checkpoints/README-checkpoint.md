# AWS Generative AI PoC : PDF RAG
#### <i>for SC&T Trading</i>

## 실행 환경
- Amazon SageMaker Studio - JupyterLab (Classic 아님)

## 주피터 노트북을 순서대로 실행하세요.
- 공통 : 01, 02 번 노트북은 환경설정 부분 입니다.
<br><br>
- <b>Complex PDF RAG</b>
  > 13 번 노트북은 OpenSearch에 PDF를 인덱싱 합니다. <br>
  > 14 번 노트북은 RAG 기반 질의 응답을 합니다.

<br>

- <b>Simple PDF RAG</b>
  > 23 번 노트북은 PDF를 PDFPlumber로 파싱하여 인덱싱 하고, RAG 기반 질의 합니다. (Hybrid Search) <br>
  > 24 번 노트북은 PDF를 LLAMA-INDEX로 파싱하여 인덱싱 하고, RAG 기반 질의 합니다. (Hybrid Search)

<br>

- <b>Simple PDF Q&A</b>
  > 31 번 노트북은 PDF를 PDFPlumber로 파싱하고, 챕터 별 요약을 수행 합니다. (no RAG) <br>
  > 32 번 노트북은 PDF를 PDFPlumber로 파싱하고 Quiz 챗봇 형태로 동작 합니다. (no RAG)

<br>

- <b>Simple PDF Summary</b>
  > 41 번 노트북은 PDF를 페이지마다 PNG로 변환해서 이미지로 Claude 에 입력하여 요약합니다. (no RAG) <br>
  > 42 번 노트북은 앞서 이미지 기반으로 정리한 내용과 PDF 파서(PyMuPdf)의 내용을 결합하여 소제목 별로 요약합니다. (no RAG)


<br>

- <b>Simple PDF Chatbot</b>
  > 51 번 노트북은 단일 PDF에 대한 챗봇 입니다. Knowledge Base for Amazon Bedrock의 "Chat with your document" 기능을 활용 합니다. <br>
  > 52 번 노트북은 단일 PDF에 대한 챗봇 입니다. 로컬 인메모리 백터 스토어인 FAISS 를 활용합니다. 


<br>

- <b>KB (Knowledge Base) 를 활용한 RAG 구현</b>
  > 61 번 노트북은 RAG에 넣을 로컬 PDF를 S3에 업로드 합니다. KB 생성은 문서를 참조하세요. <br>
  > 62 번 노트북은 앞서 생성된 KB 에 대해서 쿼리하는 샘플 코드 입니다. boto3 방식, LangChian 방식 2가지 중 선택하세요.


<br>

- <b>PDF 내용 질의 응답 시 이미지도 출력 예시</b>
  > 71 번 노트북은 로컬 PDF를 md (markdown)으로 변환하고 벡터화 합니다.(FAISS) 응답은 텍스트 및 이미지를 함께 표시합니다. <br>

<br>

## [그림] Complex PDF RAG flow
![flow](./img/complex-pdf-workflow.png)

---

Complex RAG 원본 소스는 아래 aws-samples git repo를 참조하세요.<br>
[RAG over Complex PDF on AWS](https://github.com/aws-samples/aws-ai-ml-workshop-kr/tree/c3d2185f419790905a2879284bf0c050355e0702/genai/aws-gen-ai-kr/20_applications/02_qa_chatbot/10_hands_on_lab/02_rag_over_complex_pdf)