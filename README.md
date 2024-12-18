# AWS Generative AI PoC : PDF RAG
#### <i>for SC&T Trading</i>

## 프로젝트 개요
이 프로젝트는 SC&T Trading을 위한 PDF 기반 RAG(Retrieval Augmented Generation) 시스템의 PoC(Proof of Concept)입니다. 무역 실무, 철강 시장 분석 등 다양한 PDF 문서에 대한 지능형 검색, 질의응답, 요약 기능을 제공합니다.

## 주요 기능
- Complex PDF RAG: 복잡한 구조의 PDF 문서 처리 및 질의응답
- Simple PDF RAG: PDFPlumber 또는 LLAMA-INDEX 기반의 간단한 PDF 처리
- PDF 챕터 요약 및 Quiz 챗봇
- 이미지 기반 PDF 요약
- Knowledge Base 기반 RAG 시스템
- 이미지 포함된 PDF 질의응답

## 시스템 아키텍처
![flow](./img/complex-pdf-workflow.png)

## 기술 스택
- **AWS 서비스**
  - Amazon SageMaker
  - Amazon Bedrock
  - Amazon OpenSearch
  - Amazon S3
- **주요 라이브러리**
  - LangChain
  - LLAMA-INDEX
  - PDFPlumber
  - PyMuPDF
  - FAISS

## 설치 및 환경 설정

### 필수 요구사항
- Amazon SageMaker Studio - JupyterLab (Classic 버전 미지원)
- 필요한 AWS 서비스 접근 권한

### 초기 설정
1. [01_setup.ipynb](01_setup.ipynb) 실행: 기본 환경 설정
2. [02_setup_opensearch_simple.ipynb](02_setup_opensearch_simple.ipynb) 실행: OpenSearch 설정

## 디렉토리 구조
```
.
├── img/                    # 이미지 및 PDF 파일
├── rag_data/              # RAG 시스템용 PDF 문서
├── rag_data2/            # 세분화된 무역실무 문서
└── utils/                # 유틸리티 Python 모듈
    ├── __init__.py      # 패키지 초기화
    ├── bedrock.py       # Amazon Bedrock 연동
    ├── chat.py          # 채팅 기능 구현
    ├── chunk.py         # 문서 청크 처리
    ├── common_utils.py  # 공통 유틸리티 함수
    ├── copy_generator.py # 복사본 생성 유틸리티
    ├── opensearch.py    # OpenSearch 처리
    ├── opensearch_summit.py # OpenSearch Summit 관련
    ├── proc_docs.py     # 문서 처리
    ├── pymupdf.py       # PDF 처리 (PyMuPDF)
    ├── rag.py          # RAG 핵심 기능
    ├── rag_summit.py   # RAG Summit 관련
    ├── s3.py           # Amazon S3 연동
    ├── ssm.py          # AWS Systems Manager 연동
    ├── text_to_insight.py # 텍스트 인사이트 생성
    └── text_to_report.py  # 텍스트 리포트 생성
```

## 실행 가이드

### Complex PDF RAG
- [13_load_complex_pdf_kr_opensearch.ipynb](13_load_complex_pdf_kr_opensearch.ipynb)
  - OpenSearch에 PDF 문서 인덱싱
- [14_rag_complex_doc.ipynb](14_rag_complex_doc.ipynb)
  - RAG 기반 질의응답 실행

### Simple PDF RAG
- [23_rag_text_doc.ipynb](23_rag_text_doc.ipynb)
  - PDFPlumber 기반 파싱 및 Hybrid Search
- [24_rag_text_doc-llamaIndex.ipynb](24_rag_text_doc-llamaIndex.ipynb)
  - LLAMA-INDEX 기반 파싱 및 Hybrid Search

### PDF 요약 및 Quiz
- [31_chapter-summary.ipynb](31_chapter-summary.ipynb)
  - 챕터별 PDF 요약 (RAG 미사용)
- [32_quiz-chatbot.ipynb](32_quiz-chatbot.ipynb)
  - Quiz 챗봇 구현 (RAG 미사용)

### PDF 이미지 처리
- [41_pdf2img.ipynb](41_pdf2img.ipynb)
  - PDF 페이지별 PNG 변환 및 Claude 기반 요약
- [42_pdf2img_and_summary.ipynb](42_pdf2img_and_summary.ipynb)
  - 이미지 및 텍스트 결합 소제목별 요약

### 단일 PDF 챗봇
- [51_single_PDF_query.ipynb](51_single_PDF_query.ipynb)
  - Knowledge Base for Amazon Bedrock 활용
- [52_single_PDF_query-w-FAISS.ipynb](52_single_PDF_query-w-FAISS.ipynb)
  - FAISS 기반 로컬 벡터 스토어 활용

### Knowledge Base 활용
- [61_KB_Setup.ipynb](61_KB_Setup.ipynb)
  - PDF 문서 S3 업로드 및 KB 설정
- [62_KB_Search.ipynb](62_KB_Search.ipynb)
  - boto3 또는 LangChain 기반 KB 검색

### 이미지 포함 질의응답
- [71_summarization_and_results_w_imgs.ipynb](71_summarization_and_results_w_imgs.ipynb)
  - 마크다운 변환 및 이미지 포함 응답 생성

## 참조
Complex RAG 구현은 다음 AWS 샘플을 참조했습니다:
[RAG over Complex PDF on AWS](https://github.com/aws-samples/aws-ai-ml-workshop-kr/tree/c3d2185f419790905a2879284bf0c050355e0702/genai/aws-gen-ai-kr/20_applications/02_qa_chatbot/10_hands_on_lab/02_rag_over_complex_pdf)

## 라이선스
이 프로젝트는 LICENSE 파일에 명시된 라이선스 조건에 따라 배포됩니다.
