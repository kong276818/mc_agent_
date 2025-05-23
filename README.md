# mc_agent_
Summary of Microsoft’s Research on AI Agents

📦 AI 에이전트 초급자 코스 - 환경 설정 가이드
🧭 소개
이 강좌는 Jupyter Notebook을 통해 AI 에이전트를 직접 구축해보는 실습 중심의 교육 자료입니다.
실습을 위해 GitHub 리포지토리를 포크하거나 클론하고, 필요한 설정을 완료하면 바로 시작할 수 있습니다.

🔁 리포지토리 준비
공식 리포지토리를 포크하거나 로컬로 클론합니다.

포크 후, 본인의 GitHub 계정에 복사된 리포지토리를 기준으로 실습합니다.

🚀 예제 개요
이 코스는 다음과 같은 3가지 유형의 AI 에이전트 프레임워크 예제를 제공합니다:

프레임워크	노트북 파일명	요구 사항
Semantic Kernel	semantic-kernel.ipynb	GitHub 계정
AutoGen	autogen.ipynb	GitHub 계정
Azure AI Foundry	azureaiagent.ipynb	Azure 구독

세 가지 모두 실습해본 후, 본인에게 적합한 구조를 선택해 사용하세요.

🛠️ 사전 요구사항
Python 3.12 이상

GitHub 계정 (무료)

Azure 구독 (Azure 기반 예제용)

다음 명령어로 패키지 설치:

bash
복사
편집
pip install -r requirements.txt
가상환경 사용을 권장합니다 (venv, virtualenv 등).

🔐 GitHub 기반 모델 사용 시 설정 방법
1. GitHub Personal Access Token 생성
GitHub 설정 페이지 접속

"Fine-grained tokens" 클릭 → 새 토큰 생성

이름 설정, 만료일 30일, 권한은 Public Repositories 선택

생성된 토큰 복사

2. .env 파일 설정
bash
복사
편집
cp .env.example .env
.env 파일에서 GITHUB_TOKEN= 항목에 위 토큰을 붙여넣습니다.

☁️ Azure 기반 예제 사용 시 설정 방법
1. Azure 프로젝트 연결 문자열 받기
Azure AI Foundry에서 프로젝트를 생성한 후 Overview 페이지에서 연결 문자열을 확인합니다.

2. .env 파일에 추가
bash
복사
편집
cp .env.example .env
.env 파일을 열고 PROJECT_CONNECTION_STRING= 항목에 문자열을 붙여넣습니다.

3. Azure CLI 로그인
bash
복사
편집
az login --use-device-code
로그인 후 구독(subscription)을 선택합니다.

🔧 추가 환경 변수 (Lesson 5 - Agentic RAG용)
.env 파일에 다음 항목을 추가해야 합니다:

makefile
복사
편집
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
해당 값은 Azure Portal 내 각 리소스의 Overview 및 설정 페이지에서 확인할 수 있습니다.

🧠 Keyless 인증 예시
Azure에서 인증 키를 직접 입력하지 않고 DefaultAzureCredential을 사용하는 방식:

python
복사
편집
from azure.identity import DefaultAzureCredential
credential = DefaultAzureCredential()
생성 후 토큰을 복사합니다



2단계. .env 파일 생성 및 설정

cp .env.example .env

.env 파일을 열어 GITHUB_TOKEN= 항목에 위에서 복사한 토큰을 붙여넣기

☁️ Azure AI Foundry 및 AI Agent Service 환경 설정

1단계. Azure 프로젝트 연결 문자열 받기

Azure AI Foundry 접속 후 프로젝트를 생성합니다.프로젝트 Overview 페이지에서 연결 문자열을 확인할 수 있습니다:



2단계. .env 파일 설정

cp .env.example .env

.env 파일을 열고 PROJECT_CONNECTION_STRING= 항목에 위 문자열을 복사하여 붙여넣기

3단계. Azure CLI 로그인

Azure CLI 설치 후 아래 명령어 실행:

az login --use-device-code

로그인 후 자신의 Azure 구독을 선택합니다.

🔧 RAG 예제를 위한 추가 환경 변수 설정 (lesson-5)

.env 파일에 다음 항목을 추가해야 합니다:

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

참고: 모든 항목은 Azure Portal의 프로젝트 개요, 속성, 리소스 정보 페이지 등에서 확인할 수 있습니다.

🧠 인증을 위한 Keyless 방식 사용 예시 (Azure 전용)

환경 변수 대신 Keyless 인증을 사용하려면 다음을 적용하세요:

from azure.identity import DefaultAzureCredential
credential = DefaultAzureCredential()

Azure OpenAI 또는 Search 서비스 등에 안전하게 접속할 수 있습니다.

🆘 문제 해결

설정 중 문제가 생기면 아래 경로를 통해 도움을 받을 수 있습니다:

Azure AI 커뮤니티 Discord

GitHub 이슈 제출

🎉 다음 단계

이제 실습을 위한 준비가 완료되었습니다.AI 에이전트의 세계로 함께 떠나봅시다! 🚀

➡️ 01-intro-to-ai-agents: AI 에이전트 소개 및 활용 사례 보기
