# Evidence — подтверждённые факты

Пути — относительно приватного репозитория GiftQuest (ветка `test-launch`, HEAD `4dde6e7`), если не сказано иное.

| # | Утверждение | Источник |
|---|---|---|
| 1 | В `test-launch` есть пул моделей (9 файлов `model-pool*.ts`) и только 3 листовых orch-файла: `orch-types.ts`, `orch-eligibility.ts`, `orch-effort.ts` | `git ls-tree HEAD tools/dev-factory/src`; `STATUS_REPORT.md` §1 п.5 |
| 2 | Остальные файлы оркестратора (`orch-runner`, `orch-scheduler`, `orch-graph`, `orch-worker`, `integration-*` и др.) есть только в несмерженной ветке `factory-v2-p8-6-model-pool` (в локальном клоне — как `remotes/old-pc-backup/factory-v2-p8-6-model-pool`) | `git ls-tree -r` по ветке; `STATUS_REPORT.md` §5 п.1 |
| 3 | Ветка опережает `test-launch` на 207 коммитов | `git rev-list --count test-launch..<ветка>` |
| 4 | 210 файлов, +71 948 / −2 741 | `STATUS_REPORT.md` §3.1 |
| 5 | Chaos/8.7: слово `chaos` отсутствует в `tools` и `apps` и в HEAD, и в ветке p8-6; есть только текст `p8-7` в `docs/factory-v2/FACTORY_V2_ROADMAP.md` | `git grep -il chaos` (пусто для обоих); `STATUS_REPORT.md` §5 п.2 |
| 6 | Автопилот сейчас `stopped`, ночная сессия остановлена `dirty_tree_outside_allowed_scope` (2026-09-09) | `STATUS_REPORT.md` §3.2 |
| 7 | 49 задач: done 21, blocked 16, todo 11, proposed 1 | `STATUS_REPORT.md` §3.2 |
| 8 | ≈17 000 строк `src`, 38 тестовых файлов | `STATUS_REPORT.md` §3 |
| 9 | Независимая приёмка: Harness привязан к base+candidate коммитам; QA read-only; PASS отвергается при упавшем Harness | `docs/DEVELOPER_FACTORY.md` |
| 10 | Лимиты автоодобрения: ≤5 путей, ≤3 за цикл, ≤8 за сессию, остановка после 2 подряд BLOCKED | `docs/DEVELOPER_FACTORY.md` (Policy Auto-Approve V1) |
| 11 | Дефолты автопилота: ретраи 3, таймаут задачи 45 мин, cooldown квоты 15 мин | `docs/DEVELOPER_FACTORY.md` (Autopilot) |
| 12 | Роутер — regex/keyword, Codex-first; Claude только для short architecture/research (на 2026-09-10) | `docs/factory-v2/FACTORY_V2_ARCHITECTURE.md` §1 |
| 13 | Planner V1: до 7 задач, всегда `PROPOSED` | `docs/DEVELOPER_FACTORY.md`; `FACTORY_V2_ARCHITECTURE.md` §1 |
| 14 | Lead Hunter использует пул моделей фабрики (`lead-hunter/pool-llm.ts`) | `STATUS_REPORT.md` §2.6 |
| 15 | Общий прогон vitest: 1392 / 2 / 3; падения — `lifecycle.test.ts` дашборда (EPERM) и `quality-gate.test.ts` (таймаут 5 с + EPERM) | `STATUS_REPORT.md` §2.3 |
