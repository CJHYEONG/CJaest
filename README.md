1. AI 챗봇 - 레벤슈타인 거리 기반
2. 프로젝트 소개
==>AI 개발 실무 2차 과제로 작성한 레벤슈타인 거리를 이용한 챗봇입니다.
3. 기술 스택

Python 3.x
pandas - 데이터 처리
scikit-learn - TF-IDF 및 코사인 유사도
python-Levenshtein - 레벤슈타인 거리 계산

== 파일 구조
├── chatbot_levenshtein.py    # 메인 챗봇 코드
├── ChatbotData.csv          # 학습 데이터 (질문-답변)
└── README.md               # 프로젝트 설명
가. 실행 방법
1. 필요한 라이브러리 설치
bashpip install pandas scikit-learn python-Levenshtein
2. Google Colab에서 실행
python# 라이브러리 설치
!pip install python-Levenshtein

# 코드 실행
# chatbot_levenshtein.py 파일의 코드를 복사해서 실행
3. 로컬 환경에서 실행
bashpython chatbot_levenshtein.py
📊 주요 기능
✨ 두 가지 유사도 계산 방법

TF-IDF + 코사인 유사도 - 의미적 유사성 분석
레벤슈타인 거리 - 문자열 편집 거리 기반 유사성

🔍 핵심 기능

CSV 파일에서 질문-답변 데이터 자동 로드
사용자 입력에 가장 유사한 질문 찾기
레벤슈타인 거리 상세 분석 및 시각화
실시간 챗봇 대화 기능

📈 레벤슈타인 거리란?
레벤슈타인 거리는 두 문자열 간의 유사도를 측정하는 방법으로, 한 문자열을 다른 문자열로 변환하기 위해 필요한 최소 편집 연산의 수를 의미합니다.
편집 연산의 종류:

삽입(Insertion): 문자 추가
삭제(Deletion): 문자 제거
치환(Substitution): 문자 변경

예시:
"안녕" → "안녕하세요"  거리: 3 (삽입 3회)
"cat" → "bat"         거리: 1 (치환 1회)
"kitten" → "sitting"   거리: 3 (치환 2회, 삽입 1회)
🎯 사용 예시
python# 챗봇 객체 생성
chatbot = SimpleChatBot('/content/sample_data/ChatbotData.csv')

# 레벤슈타인 거리 기반 답변
response = chatbot.find_best_answer_levenshtein("안녕")
print(response)  # "안녕하세요! 무엇을 도와드릴까요?"

# 가장 유사한 질문 분석
result = find_most_similar_question_index("안녕", questions)
📝 결과 예시
🔍 입력 문장: '안녕'
============================================================
인덱스 0: '안녕하세요' → 거리: 3
인덱스 1: '오늘 날씨가 어때요?' → 거리: 8
인덱스 2: '고마워요' → 거리: 4
============================================================
🎯 가장 유사한 질문 인덱스: 0
📝 가장 유사한 질문: '안녕하세요'
📏 최소 레벤슈타인 거리: 3
🎓 학습 내용
이 프로젝트를 통해 학습할 수 있는 내용:

자연어 처리 기초: TF-IDF, 벡터화
유사도 계산: 코사인 유사도, 레벤슈타인 거리
Python 라이브러리: pandas, scikit-learn
객체지향 프로그래밍: 클래스 설계 및 구현
