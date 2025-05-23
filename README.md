# mc_agent_
Summary of Microsoft’s Research on AI Agents

# 📦 AI 에이전트 초급자 코스 - 환경 설정 가이드 (Course Setup Guide)

## 🧭 소개 (Introduction)

이 강좌에서는 제공된 Jupyter Notebook 코드 예제를 실행할 수 있도록 환경을 설정하는 방법을 안내합니다. GitHub 리포지토리를 클론하거나 포크하고, 필요한 토큰 및 환경 변수를 설정하면 실습을 바로 시작할 수 있습니다.

---

## 🔁 리포지토리 클론 또는 포크하기

먼저 본 GitHub 리포지토리를 클론하거나 포크하세요.  
자신의 GitHub 계정에 복사본을 생성하면 직접 코드를 실행하고 수정해 볼 수 있습니다.

👉 [원본 리포지토리 보기](https://github.com/microsoft/ai-agents-for-beginners)

---

## 🚀 코드 실행 개요

이 코스는 세 가지 프레임워크 기반의 Jupyter Notebook 예제를 제공합니다.

| 프레임워크 유형 | 노트북 이름 | 필요 사항 |
|----------------|-------------|------------|
| Semantic Kernel Framework | `semantic-kernel.ipynb` | GitHub 계정 필요 |
| AutoGen Framework | `autogen.ipynb` | GitHub 계정 필요 |
| Azure AI Foundry + AI Agent Service | `azureaiagent.ipynb` | Azure 구독 필요 |

---

## 🛠️ 사전 요구사항 (Requirements)

- Python 3.12+
- GitHub 계정 (GitHub Models Marketplace 사용용)
- Azure 구독 (Azure AI Foundry/Agent Service 사용 시)
- Python 패키지 설치:
  
```bash
pip install -r requirements.txt

가상환경(virtualenv 또는 venv) 사용을 권장합니다.

GitHub 기반 모델 사용 환경 설정
1단계. GitHub Personal Access Token 발급
GitHub 계정 접속 → Settings > Developer Settings > Personal Access Tokens

Fine-grained tokens 클릭 → Generate new token

이름 입력, 만료일(권장: 30일), 권한: Public Repositories 체크

생성 후 나오는 토큰 값을 복사

2단계. .env 파일 생성 및 설정
cp .env.example .env

.env 파일을 열어 GITHUB_TOKEN= 항목에 위에서 복사한 토큰을 붙여넣기

Azure AI Foundry 및 AI Agent Service 환경 설정
1단계. 프로젝트 및 연결 문자열 생성
Azure AI Foundry 접속 → 프로젝트 생성

프로젝트 Overview 페이지 → Project Connection String 복사

cp .env.example .env

.env 파일에서 PROJECT_CONNECTION_STRING= 항목에 복사한 값을 붙여넣기

3단계. Azure CLI 로그인

Azure CLI 설치 후 다음 명령어 실행:
az login --use-device-code


로그인 후 구독(subscription)을 선택

 RAG 예제를 위한 추가 환경 변수 설정 (lesson-5용)
다음 변수를 .env 파일에 추가해야 합니다:

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
참고: 이 값들은 Azure Portal 내 각 프로젝트 Overview 또는 관련 리소스 페이지에서 확인할 수 있습니다.

🧠 인증을 위한 Keyless 방식 사용 예시 (Azure 전용)
환경 변수에 직접 Key를 쓰지 않고 인증하려면 azure.identity 모듈의 DefaultAzureCredential을 사용하세요:

python
복사
편집
from azure.identity import DefaultAzureCredential
credential = DefaultAzureCredential()
Azure OpenAI 또는 Azure Search 등에 사용할 수 있습니다.

🆘 문제 해결
셋업 과정에서 문제가 발생하면 Azure AI 커뮤니티 Discord 또는 이 리포지토리에 이슈를 남겨주세요.

🎉 다음 단계
이제 실습을 위한 준비가 완료되었습니다.
AI 에이전트의 세계로 함께 떠나봅시다! 🚀

yaml
복사
편집

---

필요하면 이 파일을 `.md`로 저장해 GitHub 저장소 루트에 `course-setup.md` 혹은 `README_ko.md` 형태로 바로 업로드하시면 됩니다.  
또한, 원하시면 영어/한글 병기 버전도 만들어드릴 수 있어요.
