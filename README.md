# math-report
import React from "react";

export default function HabitReport() {
  const student = {
    name: "홍길동",
    gradeClass: "중2 / 2반",
    period: "2025년 4월 8일 ~ 2025년 7월 7일",
    teacher: "김수정 선생님",
    goal: "매일 40분 이상 수학 공부 / 오답노트 작성 습관 들이기",
    routine: "평일 매일 수학 학습 / 주 1회 테스트 / 개념 정리 노트 작성",
    habitStats: [
      { period: "1~4주", studyRate: "80%", notes: 3, wrongNotes: 5, avgTime: "35분" },
      { period: "5~8주", studyRate: "92%", notes: 6, wrongNotes: 8, avgTime: "42분" },
      { period: "9~12주", studyRate: "95%", notes: 6, wrongNotes: 9, avgTime: "47분" },
    ],
    tests: [
      { name: "1주차 진단 테스트", score: 62, feedback: "개념 이해 부족 / 실수 다수" },
      { name: "5주차 중간 테스트", score: 75, feedback: "유형 익숙해짐 / 오답 감축" },
      { name: "12주차 최종 테스트", score: 85, feedback: "개념 + 응용력 모두 향상됨" },
    ],
    teacherComment:
      "처음엔 스스로 계획 세우는 게 어려워 보였지만, 점차 루틴을 조정하고 오답을 정리하는 모습이 인상 깊었습니다.",
    studentReflection:
      "예전엔 수학이 답답했는데, 이제는 내가 어떻게 공부해야 하는지 조금 알게 된 것 같아요!",
    nextSuggestions: [
      "응용 문제 풀이 시, 풀이 과정을 더 명확히 적어보기",
      "단원별 개념 정리를 월 1회 복습 루틴으로 반복할 것",
    ],
  };

  return (
    <div className="p-6 max-w-4xl mx-auto bg-white rounded-2xl shadow-md space-y-6">
      <h1 className="text-2xl font-bold text-blue-700">
        📘 {student.name} 3개월 수학 습관 성장 리포트
      </h1>

      <section className="space-y-1">
        <h2 className="text-xl font-semibold">📌 기본 정보</h2>
        <p>학생 이름: {student.name}</p>
        <p>학년/반: {student.gradeClass}</p>
        <p>수업 기간: {student.period}</p>
        <p>담당 선생님: {student.teacher}</p>
      </section>

      <section className="space-y-2">
        <h2 className="text-xl font-semibold">🎯 목표 및 루틴 설정</h2>
        <p>초반 목표: {student.goal}</p>
        <p>설정된 루틴: {student.routine}</p>
      </section>

      <section className="space-y-2">
        <h2 className="text-xl font-semibold">📈 습관 실천 현황</h2>
        <table className="w-full table-auto border text-sm">
          <thead>
            <tr className="bg-gray-100">
              <th>기간</th>
              <th>학습 실천률</th>
              <th>개념 정리 노트</th>
              <th>오답노트</th>
              <th>일 평균 학습 시간</th>
            </tr>
          </thead>
          <tbody>
            {student.habitStats.map((item, idx) => (
              <tr key={idx} className="text-center border-t">
                <td>{item.period}</td>
                <td>{item.studyRate}</td>
                <td>{item.notes}회</td>
                <td>{item.wrongNotes}회</td>
                <td>{item.avgTime}</td>
              </tr>
            ))}
          </tbody>
        </table>
      </section>

      <section className="space-y-2">
        <h2 className="text-xl font-semibold">📊 테스트 점수 변화</h2>
        <table className="w-full table-auto border text-sm">
          <thead>
            <tr className="bg-gray-100">
              <th>테스트명</th>
              <th>점수</th>
              <th>피드백 요약</th>
            </tr>
          </thead>
          <tbody>
            {student.tests.map((test, idx) => (
              <tr key={idx} className="text-center border-t">
                <td>{test.name}</td>
                <td>{test.score}점</td>
                <td>{test.feedback}</td>
              </tr>
            ))}
          </tbody>
        </table>
      </section>

      <section>
        <h2 className="text-xl font-semibold">🧠 담당 선생님 피드백</h2>
        <p className="italic text-gray-700 mt-1">“{student.teacherComment}”</p>
      </section>

      <section>
        <h2 className="text-xl font-semibold">💬 학생 한줄 소감</h2>
        <p className="italic text-gray-700 mt-1">“{student.studentReflection}”</p>
      </section>

      <section className="space-y-1">
        <h2 className="text-xl font-semibold">📝 다음 학습 제안</h2>
        <ul className="list-disc pl-6">
          {student.nextSuggestions.map((tip, idx) => (
            <li key={idx}>{tip}</li>
          ))}
        </ul>
      </section>
    </div>
  );
}
