# mc_agent_
Summary of Microsoft’s Research on AI Agents

\documentclass\[12pt]{article}
\usepackage\[utf8]{inputenc}
\usepackage{kotex}
\usepackage{hyperref}
\usepackage{longtable}
\usepackage{listings}
\usepackage{color}
\usepackage{geometry}
\geometry{a4paper, margin=1in}
\definecolor{codegray}{gray}{0.95}
\lstset{
backgroundcolor=\color{codegray},
basicstyle=\ttfamily\footnotesize,
breaklines=true,
frame=single
}

\title{AI 에이전트 초급자 코스 - 환경 설정 가이드}
\author{}
\date{}

\begin{document}

\maketitle

\section\*{소개}
이 강좌는 Jupyter Notebook을 통해 AI 에이전트를 직접 구축해보는 실습 중심의 교육 자료입니다. 실습을 위해 GitHub 리포지토리를 포크하거나 클론하고, 필요한 설정을 완료하면 바로 시작할 수 있습니다.

\section\*{리포지토리 준비}
공식 리포지토리를 포크하거나 로컬로 클론합니다. 포크 후, 본인의 GitHub 계정에 복사된 리포지토리를 기준으로 실습합니다.

\section\*{예제 개요}
이 코스는 다음과 같은 3가지 유형의 AI 에이전트 프레임워크 예제를 제공합니다:

\begin{longtable}{|p{4cm}|p{6cm}|p{3cm}|}
\hline
\textbf{프레임워크} & \textbf{노트북 파일명} & \textbf{요구 사항} \ \hline
Semantic Kernel & \texttt{semantic-kernel.ipynb} & GitHub 계정 \ \hline
AutoGen & \texttt{autogen.ipynb} & GitHub 계정 \ \hline
Azure AI Foundry & \texttt{azureaiagent.ipynb} & Azure 구독 \ \hline
\end{longtable}

\section\*{사전 요구사항}
\begin{itemize}
\item Python 3.12 이상
\item GitHub 계정 (무료)
\item Azure 구독 (Azure 기반 예제용)
\end{itemize}

\textbf{패키지 설치:}
\begin{lstlisting}\[language=bash]
pip install -r requirements.txt
\end{lstlisting}

가상환경 사용을 권장합니다 (venv, virtualenv 등).

\section\*{GitHub 기반 모델 설정}
\subsection\*{1단계: GitHub Personal Access Token 생성}
\begin{itemize}
\item GitHub 설정 페이지 접속
\item Fine-grained tokens 클릭 → 새 토큰 생성
\item 이름 설정, 만료일 30일, 권한: Public Repositories 선택
\item 생성된 토큰 복사
\end{itemize}

\subsection\*{2단계: .env 파일 설정}
\begin{lstlisting}\[language=bash]
cp .env.example .env
\end{lstlisting}

.env 파일에서 \texttt{GITHUB\_TOKEN=} 항목에 위에서 복사한 토큰을 붙여넣습니다.

\section\*{Azure 기반 모델 설정}
\subsection\*{1단계: Azure 프로젝트 연결 문자열 받기}
Azure AI Foundry에서 프로젝트를 생성한 후 Overview 페이지에서 연결 문자열을 확인합니다.

\subsection\*{2단계: .env 파일 설정}
\begin{lstlisting}\[language=bash]
cp .env.example .env
\end{lstlisting}

.env 파일에서 \texttt{PROJECT\_CONNECTION\_STRING=} 항목에 문자열을 붙여넣습니다.

\subsection\*{3단계: Azure CLI 로그인}
\begin{lstlisting}\[language=bash]
az login --use-device-code
\end{lstlisting}

로그인 후 구독(subscription)을 선택합니다.

\section\*{추가 환경 변수 (Lesson 5 - Agentic RAG용)}
\texttt{.env} 파일에 다음 항목을 추가하세요:

\begin{lstlisting}\[language=make]
AZURE\_SUBSCRIPTION\_ID=
AZURE\_AI\_PROJECT\_NAME=
AZURE\_OPENAI\_SERVICE=
AZURE\_OPENAI\_RESOURCE\_GROUP=
GLOBAL\_LLM\_SERVICE=
AZURE\_OPENAI\_EMBEDDING\_DEPLOYMENT\_NAME=
AZURE\_OPENAI\_CHAT\_DEPLOYMENT\_NAME=
AZURE\_OPENAI\_ENDPOINT=
AZURE\_OPENAI\_API\_KEY=
AZURE\_SEARCH\_SERVICE\_ENDPOINT=
AZURE\_SEARCH\_API\_KEY=
AZURE\_OPENAI\_API\_VERSION=
\end{lstlisting}

모든 값은 Azure Portal의 Overview 및 설정 페이지에서 확인할 수 있습니다.

\section\*{Keyless 인증 예시}
\begin{lstlisting}\[language=python]
from azure.identity import DefaultAzureCredential
credential = DefaultAzureCredential()
\end{lstlisting}

\section\*{문제 해결}
\begin{itemize}
\item \href{[https://discord.gg/kzRShWzttr}{Azure](https://discord.gg/kzRShWzttr}{Azure) AI 커뮤니티 Discord}
\item \href{[https://github.com/microsoft/ai-agents-for-beginners/issues}{GitHub](https://github.com/microsoft/ai-agents-for-beginners/issues}{GitHub) 이슈 등록}
\end{itemize}

\section\*{다음 단계}
이제 실습을 위한 준비가 완료되었습니다. AI 에이전트의 세계로 함께 떠나봅시다! 🚀\\
\href{../01-intro-to-ai-agents/README.md}{01-intro-to-ai-agents: AI 에이전트 소개 및 활용 사례 보기}

\end{document}

