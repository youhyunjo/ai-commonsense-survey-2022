Survey on AI Common Sense

## 데이터

- [data/survey01.tsv](data/survey01.tsv): 설문1 (AI에게 '상식'을 가르친다면)
- [data/survey02.tsv](data/survey02.tsv): 설문2 (일상생활 친밀대화)

### 설문1

- [data/survey01.tsv](data/survey01.tsv): 설문1 (AI에게 '상식'을 가르친다면)
- 총 36명이 60 문항에 답한 2160 개의 응답 확보.
- '주어진 문장이 AI에 학습시키기에 적합한가?'라는 질문에 대해 'O(예)/X(아니오)'로 응답.
- 필요한 경우 자신의 응답에 대한 판단 이유를 메모로 남길 수 있음.

컬럼:

| colname        | desc              | value |
|----------------|-------------------|-------|
| `subject_id`   | 참여자 고유번호   | `s01f2`, ..., `s365m6` |
| `gender`       | 참여자 성별       |  남, 여     |
| `age`          | 참여자 나이       |  20대, 30대, 40대, 50대, 60대     |
| `trial`        | 설문 순서         |  `1-60`     |
| `cse_id`       | 상식표현 고유번호 |  `cse001`, ..., `cse060`     |
| `priority`     | 상식표현 중요도   |  필수, 주변     |
| `domain`       | 상식표현 영역     | 식음료, 주거와생활, 상거래, 미용과건강, 여가생활       |
| `keyword`      | 상식표현 키워드   |  밥, 집, 옷, 날씨, 다이어트, 게임     |
| `response`     | 설문 응답  | O, X      |
| `y`            | 설문 응답  | 1, 0      |
| `cse_sentence` | 상식표현 문장 | 계란이랑 햄을 사서 볶음밥을 하려고 한다.  |
| `note`         | 참여자 메모   |       |


tables:

- [data/tables/subject.tsv](data/tables/subject.tsv): 참여자 정보
- [data/tables/commonsense\_expression.tsv](data/tables/commonsense_expression.tsv): 상식표현 정보 (설문 항목 정보)
- [data/tables/survey01\_response.tsv](data/tables/survey01_response.tsv): 설문 응답 정보


### 설문2

- [data/survey02.tsv](data/survey02.tsv): 설문2 (일상생활 친밀대화)
- 총 36명이 60 문항에 답한 2160개의 응답 확보.
- 주어진 사람의 '질문에 대한 대답으로 일상생활에서 더 자주 들을 수 있는,
  친밀감이 느껴지는 답변을 선택'하는 설문. 
- 주어진 2개의 대답 중 선택하거나 자유롭게 기타 의견을 작성할 수 있음. 주어진
  한 대답은 기본(base)적인 챗봇 대화이며 다른 하나는 상식(sense)이 적용된
  대화임.

| colname          | desc               | value                                                 |
|------------------|--------------------|-------------------------------------------------------|
| `subject_id`     | 참여자 고유번호    | `s01f2`, ..., `s365m6`                                |
| `gender`         | 참여자 성별        | 남, 여                                                |
| `age`            | 참여자 나이        | 20대, 30대, 40대, 50대, 60대                          |
| `trial`          | 설문 순서          | `1-60`                                                |
| `query_id`       | 인간 질의 고유번호 | `query001`, ..., `query060`                           |
| `priority`       | 대화 중요도        | 필수, 주변                                            |
| `domain`         | 대화 영역          | 식음료, 주거와생활, 상거래, 미용과건강, 여가생활      |
| `keyword`        | 대화 키워드        | 밥, 집, 옷, 날씨, 다이어트, 게임                      |
| `human_query`    | 질의 문장          | 김치볶음밥 먹어야지.                                                       |
| `response`       | 설문 응답          | base, sense, other                                    |
| `chat_id`        | 챗봇 대화 고유번호 | `chat001_base`, `chat001_sense`, ..., `chat060_sense` |
| `chatbot_answer` | 챗봇 대화 문장     | 계란이랑 햄 넣은 김치볶음밥이 맛있어요.                                                      |


tables:

- [data/tables/subject.tsv](data/tables/subject.tsv): 참여자 정보
- [data/tables/chatbot\_query\_answer.tsv](data/tables/chatbot_query_answer.tsv): 챗봇 대화 정보 (설문 항목 정보)
- [data/tables/survey02\_response.tsv](data/tables/survey02_response.tsv): 설문 응답 정보
- [data/tables/survey02\_response\_note.tsv](data/tables/survey02_response_note.tsv): 설문 참여자 종합 의견
- [data/tables/chatbot\_answer\_to\_commonsense.tsv](data/tables/chatbot_answer_to_commonsense.tsv): 챗봇 대화 생성의 근거가 된 상식표현 매핑

### 참여자

- [data/tables/subject.tsv](data/tables/subject.tsv): 설문 참여자 정보. 성별과 나이.
- 총 36명 참여.

컬럼

| colname      | desc            | value                        |
|--------------|-----------------|------------------------------|
| `subject_id` | 참여자 고유번호 | `s01f2`, ..., `s365m6`       |
| `name_hash`  | 참여자 익명화   |                              |
| `gender`     | 참여자 성별     | 남, 여                       |
| `age`        | 참여자 나이     | 20대, 30대, 40대, 50대, 60대 |


규모

| 성별 | 20대 | 30대 | 40대 | 50대 | 60대 | 합계 |
|------|------|------|------|------|------|------|
| 남성 | 6    | 6    | 3    | 2    | 1    | 18   |
| 여성 | 6    | 6    | 3    | 3    | 0    | 18   |
| 합계 | 12   | 12   | 6    | 5    | 1    | 36   |


### 상식표현

- [data/tables/commonsense\_expression.tsv](data/tables/commonsense_expression.tsv)
- 일상생활의 상식을 엿볼 수 있는 내용의 문장
- 총 60 문항으로 구성. 핵심 영역 3개와 주변 영역 3개에 대해 각각 10개 문항으로 구성.

컬럼 

| colname      | desc            | value                        |
|--------------|-----------------|------------------------------|
| `cse_id`       | 상식표현 고유번호 |  `cse001`, ..., `cse060`     |
| `priority`     | 상식표현 중요도   |  필수, 주변     |
| `domain`       | 상식표현 영역     | 식음료, 주거와생활, 상거래, 미용과건강, 여가생활       |
| `keyword`      | 상식표현 키워드   |  밥, 집, 옷, 날씨, 다이어트, 게임     |
| `cse_sentence` | 상식표현 문장 | 계란이랑 햄을 사서 볶음밥을 하려고 한다.  |


규모

| 중요도 | 영역       | 키워드   | 문항수 |
|--------|------------|----------|--------|
| 핵심   | 식음료     | 밥       | 10     |
| 핵심   | 주거와생활 | 집       | 10     |
| 핵심   | 상거래     | 옷       | 10     |
| 주변   | 주거와생활 | 날씨     | 10     |
| 주변   | 미용과건강 | 다이어트 | 10     |
| 주변   | 여가생활   | 게임     | 10     |

### 챗봇 대화


- [data/tables/chatbot\_query\_answer.tsv](data/tables/chatbot_query_answer.tsv): 챗봇 대화 정보 (설문 항목 정보)
- 인간 질의와 챗봇 답변의 가상적인 짝 데이터. 하나의 질의에 대해 기본(base) 답변과 상식(sense) 장착 답변 짝 제시.
- 기본(base) 답변 출처: <https://github.com/songys/Chatbot_data>

| colname      | desc            | value                        |
|--------------|-----------------|------------------------------|
| `query_id`       | 인간 질의 고유번호 | `query001`, ..., `query060`                           |
| `priority`       | 대화 중요도        | 필수, 주변                                            |
| `domain`         | 대화 영역          | 식음료, 주거와생활, 상거래, 미용과건강, 여가생활      |
| `keyword`        | 대화 키워드        | 밥, 집, 옷, 날씨, 다이어트, 게임                      |
| `human_query`    | 질의 문장          | 김치볶음밥 먹어야지.                                   |
| `chat_id`        | 챗봇 대화 고유번호 | `chat001_base`, `chat001_sense`, ..., `chat060_sense` |
| `chat_mode`      | 챗봇 대화 모드   | `base`, `sense` |
| `chatbot_answer` | 챗봇 대화 문장     | 계란이랑 햄 넣은 김치볶음밥이 맛있어요.                     |


규모

| 중요도 | 영역       | 키워드   | 질의 항목수 |
|--------|------------|----------|-------------|
| 핵심   | 식음료     | 밥       | 10          |
| 핵심   | 주거와생활 | 집       | 10          |
| 핵심   | 상거래     | 옷       | 10          | 
| 주변   | 주거와생활 | 날씨     | 10          | 
| 주변   | 미용과건강 | 다이어트 | 10          | 
| 주변   | 여가생활   | 게임     | 10          | 





