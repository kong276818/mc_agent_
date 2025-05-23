# mc_agent_
Summary of Microsoft’s Research on AI Agents

📦 AI 에이전트 초급자 코스 - 환경 설정 가이드 (Course Setup Guide)

🧭 소개 (Introduction)

이 강좌에서는 제공된 Jupyter Notebook 코드 예제를 실행할 수 있도록 환경을 설정하는 방법을 안내합니다. GitHub 리포지토리를 클론하거나 포크하고, 필요한 토큰 및 환경 변수를 설정하면 실습을 바로 시작할 수 있습니다.

🔁 리포지토리 클론 또는 포크하기

먼저 본 GitHub 리포지토리를 클론하거나 포크하세요.자신의 GitHub 계정에 복사본을 생성하면 직접 코드를 실행하고 수정해 볼 수 있습니다.

👉 포크(Fork)하기

포크하면 다음과 같이 자신의 리포지토리에 복사됩니다:

![image](https://github.com/user-attachments/assets/16aa5774-7b5a-4f15-aecc-967f67a7d46c)


🚀 코드 실행 개요

이 코스는 세 가지 프레임워크 기반의 Jupyter Notebook 예제를 제공합니다.

프레임워크 유형

노트북 이름

필요 사항

Semantic Kernel Framework

semantic-kernel.ipynb

GitHub 계정 필요

AutoGen Framework

autogen.ipynb

GitHub 계정 필요

Azure AI Foundry + AI Agent Service

azureaiagent.ipynb

Azure 구독 필요

세 가지 예제를 모두 실습해보고, 본인에게 맞는 환경을 선택하세요.

🛠️ 사전 요구사항 (Requirements)

Python 3.12+

GitHub 계정 (GitHub Models Marketplace 사용용)

Azure 구독 (Azure AI Foundry/Agent Service 사용 시)

Python 패키지 설치:

pip install -r requirements.txt

가상환경(virtualenv 또는 venv) 사용을 권장합니다.

🔐 GitHub 기반 모델 사용 환경 설정

1단계. GitHub Personal Access Token 발급

GitHub 계정 접속 → Personal Access Tokens 설정

왼쪽에서 Fine-grained tokens 선택 후 Generate new token 클릭

이름 설정, 만료일(권장: 30일), 권한: Public Repositories 체크

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
