# ms_agent_Summary00 KR 
Summary of Microsoft’s Research on AI Agents

# 🧠 Microsoft AI Agents - 초급자 실습 가이드

이 프로젝트는 **Jupyter Notebook**을 통해 Microsoft의 대표적인 AI 에이전트 프레임워크를 직접 실습해보는 코스입니다.  
아래의 단계를 따라 환경을 설정하고, 실제로 AI 에이전트를 구축해보세요!

---

## 📦 리포지토리 준비

1. 공식 GitHub 리포지토리를 포크하거나 클론합니다.
2. 로컬 환경에서 아래 명령어를 실행합니다:
![image](https://github.com/user-attachments/assets/d0ce0903-4cf3-4ff7-b678-a71e4c2f9807)


git clone https://github.com/YOUR_USERNAME/microsoft-ai-agents-course.git
cd microsoft-ai-agents-course
## 🚀 제공 예제 개요

| 프레임워크         | 노트북 파일명             | 요구 사항         |
|--------------------|---------------------------|--------------------|
| Semantic Kernel    | `semantic-kernel.ipynb`   | GitHub 계정 필요   |
| AutoGen            | `autogen.ipynb`           | GitHub 계정 필요   |
| Azure AI Foundry   | `azureaiagent.ipynb`      | Azure 구독 필요   |

세 가지 예제를 모두 실행해보고, 자신에게 맞는 프레임워크를 선택하세요.

## 🛠️ 사전 요구 사항
Python 3.12 이상

GitHub 계정 (무료)

Azure 구독 (Azure 기반 예제용)

```bash
pip install -r requirements.txt
```
※ 가상환경 사용을 권장합니다 (venv, virtualenv 등)

## 🔐 GitHub 기반 예제 설정 방법
1. GitHub Personal Access Token 생성
GitHub → 설정 → Developer settings → Fine-grained tokens 진입

이름 설정, 만료일 30일, 권한은 Public Repositories

생성 후 토큰 복사
![image](https://github.com/user-attachments/assets/737d1621-7360-4dea-a809-da825b5d61bc)

## 2. .env 파일 설정

```bash
cp .env.example .env
```
.env 파일 열어서 다음 항목 수정:
```bash
GITHUB_TOKEN=복사한_토큰
```
![image](https://github.com/user-attachments/assets/772545fa-43e1-48dd-bc6e-17ddc4aff53a)

## ☁️ Azure 기반 예제 설정 방법
1. 프로젝트 연결 문자열 받기
Azure AI Foundry에서 프로젝트 생성 후
Overview 페이지에서 연결 문자열 복사

## 2. .env 파일 설정

```bash
cp .env.example .env
```
.env 파일 열어서 다음 항목 수정:
```bash
PROJECT_CONNECTION_STRING=복사한_연결_문자열
```

## 3. Azure CLI 로그인
Azure CLI 설치 후:
```bash
az login --use-device-code
```

로그인 후 구독을 선택합니다.

## 🔧 Agentic RAG 예제 추가 설정 (Lesson 5)
.env 파일에 아래 항목들을 추가해야 합니다:

```bash
AZURE_SUBSCRIPTION_ID=
AZURE_AI_PROJECT_NAME=
AZURE_OPENAI_SERVICE=
AZURE_OPENAI_RESOURCE_GROUP=
GLOBAL_LLM_SERVICE=
AZURE_OPENAI_EMBEDDING_DEPLOYMENT_NAME=
AZURE_OPENAI_CHAT_DEPLOYMENT_NAME=
AZURE_OPENAI_ENDPOINT=
AZURE_OPENAI_API_KEY=
AZURE_SEARCH_SERVICE_ENDPOINT=
AZURE_SEARCH_API_KEY=
AZURE_OPENAI_API_VERSION=
```

모든 값은 Azure Portal에서 프로젝트/리소스의 개요 또는 속성 페이지에서 확인할 수 있습니다.

## 🧠 Keyless 인증 예시 (Azure 전용)

환경 변수 대신 Azure의 기본 인증 시스템을 사용하는 예시:

```bash
from azure.identity import DefaultAzureCredential
credential = DefaultAzureCredential()
OpenAI 또는 Search 리소스에 보다 안전하게 접근할 수 있습니다.
```
