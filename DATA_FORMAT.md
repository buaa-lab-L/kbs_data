# Data format / 数据格式

## Array and time convention

- Format: NumPy `.npy`, one-dimensional finite floating-point array; no object/pickle payload.
- Values: fractions of rated power; for example, 0.5 denotes 50% of rated power.
- Sampling interval: 1 second.
- `H`: number of control intervals, also the final time in seconds.
- Number of stored samples: `H+1`, at times 0, 1, ..., H seconds.
- Use all `H` intervals. Do not truncate profiles longer than 200 seconds.
- Curve count: 100. Horizon range: 200–433 seconds. Total: 24,894 intervals.

数组为一维有限浮点数，单位为额定功率比例，采样间隔1秒。`H`表示完整控制区间数，数组长度必须是`H+1`。不同曲线时域不同，应逐条读取清单中的`H`，不将长曲线截断到200秒。

## Manifest fields

| Field | Meaning |
| --- | --- |
| `curve_id` | Stable identifier retained from the frozen dataset |
| `path` | Relative path of the NPY array within this package |
| `H` | Full number of control intervals |
| `sha256` | SHA-256 of the exact NPY file bytes |
| `family` | Original profile family label |

## Profile families

| Family | Count |
| --- | ---: |
| `test_trend_deep` | 50 |
| `double_deep_plateaus` | 24 |
| `staged_recovery` | 10 |
| `single_deep_hold_recover` | 7 |
| `test_like_quick_rebound` | 5 |
| `double_dip_short_holds` | 4 |
