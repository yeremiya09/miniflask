# a survey using flask
#### flask를 이용한 설문조사
---

### Execution Guide
- Installation
```
pip3 install flask
pip3 install plotly
pip3 install flask-migrate
pip3 install pandas
pip3 install sqlalchemy
```
- Initialize DB
```
flask init-db
```
- Execution
```
flask run
```




---

### Demo
<details>
<summary>survey ver</summary>

![ver_survey](./img/ver_survey.gif)
</details>
<details>
<summary>admin ver</summary>

![ver_admin](./img/ver_admin.gif)
</details>

---
<details>
<summary>중요기능</summary>

### Routes

- `route(rule, **options)`
    - 매개변수 `rule`에 URL을... 그리고 `options`에 HTTP 메소드 CRUD, 즉 POST, GET, PUT, DELETE를 입력받아 맵핑합니다.
- 설문 응답자 정보 수집 `add_participant()`
    - 설문을 시작하면 설문을 시작하기에 앞서 설문 응답자의 정보를 수집하는 route
    - 설문 응답자의 이름, 나이대, 성별을 JSON 형태로 수집하고, 설문 응답자의 ID를 반환하며 quiz 페이지를 리다이렉션
    <details>
    <summary>code</summary>

    ![def_add_participant()](/img/def_add_participant.png)
    
    </details>
- 설문 시작 `quiz()`
    - 데이터베이스에 저장된 설문 항목들을 불러오며 설문 시작
    - 설문 응답자의 ID 값이 없으면 home으로 돌아감
    - DB에서 설문 항목들을 불러와 차례대로 렌더링
    <details>
    <summary>code</summary>

    ![def_quiz()](/img/def_quiz.png)
    
    </details>
- 결과 출력 `show_results()`
    - 설문 응답자들의 나이, 성별과 설문 항목별 응답 내용을 pandas Dataframe으로 변환하고, Plotly를 사용해 그래프로 시각화한 것을 JSON으로 전달하여 결과화면에서 렌더링합니다

</details>

---

<details>


</details>

---
### DB Relationship
