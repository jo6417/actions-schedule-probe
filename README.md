# actions-schedule-probe

GitHub Actions의 예약(cron) 실행이 얼마나 밀리는지 재기 위한 측정용 리포.

`jo6417/release-tracker`의 알림이 2026-08-26 GitHub Actions 장애 이후
2~7시간씩 밀리는데, 그것이 그 리포 고유의 상태인지 GitHub 전반의 문제인지
가르기 위한 **대조군**이다. 예약 이력이 없는 깨끗한 리포에서 같은 조건으로
잰다.

- `probe-oclock`  : `0 0 * * *`  — release-tracker와 동일한 정각 슬롯
- `probe-offset`  : `37 0 * * *` — 같은 조건, 분만 다름

하는 일은 `date` 한 줄이 전부다. 시크릿을 쓰지 않는다.
측정이 끝나면 리포째 삭제한다.
