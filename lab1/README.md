# Лабораторная работа № 1 — ГА для многомерной непрерывной оптимизации

**Вариант V = 17** (N = 10, Q = 0, Y = 26): функция различных степеней
f(x) = Σ |x_i|^(i+1), x ∈ [-1, 1]^10, глобальный минимум f* = 0 в x* = 0.

Всё содержимое (код, эксперименты, графики, отчёт) находится в ноутбуке `lab1.ipynb`.

## Установка и запуск

Нужны Python ≥ 3.10 и пакеты `numpy`, `pandas`, `matplotlib`, `scipy`, `jupyter`:

```bash
pip install numpy pandas matplotlib scipy jupyter
cd lab1
jupyter notebook lab1.ipynb          # интерактивно
# или выполнить целиком без интерфейса (~1 мин):
jupyter nbconvert --to notebook --execute --inplace lab1.ipynb
```

Ноутбук нужно запускать из папки `lab1`: результаты сохраняются в `lab1/results/`.

## Воспроизводимость

* Все параметры собраны в `GAConfig` (раздел 1.6); базовая конфигурация лежит в `results/base_config.csv`.
* Серия из 30 запусков использует seed `1000..1029` (параметры `N_RUNS`, `BASE_SEED`).
  Отдельный запуск воспроизводится вызовом `run_ga(GAConfig(), seed)`.

## Результаты (`results/`)

| Файл | Содержимое |
|---|---|
| `runs_*.csv` | итоги каждого запуска: seed, лучшее f, число вычислений, время |
| `summary_*.csv` | статистики серий: best / mean / median / std / worst / доля успехов / p-value |
| `convergence_*.png`, `factor_*.png` | графики сходимости и диаграммы размаха |
| `sigma_adaptation.png` | динамика самоадаптивного σ |
| `demo_d2_population.png` | популяция на линиях уровня при d = 2 |
