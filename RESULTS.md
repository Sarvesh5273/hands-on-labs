# TORCS Learning Lab Results - May Challenge

## Baseline Parameters
* TARGET_SPEED = 100
* STEER_GAIN = 30
* CENTERING_GAIN = 0.20
* BRAKE_THRESHOLD = 0.9
* ENABLE_TRACTION_CONTROL = True

## Modifications & Experimental Log

### Run 1: High-Speed Aggression
* **Parameters Changed**: `TARGET_SPEED = 150`, `BRAKE_THRESHOLD = 0.6`
* **Observed/Expected Effect**: The vehicle accelerates rapidly on straightaways, but lowering the brake threshold causes late braking into sharp corners. The car struggles with severe understeer, slipping past the apex and losing track positioning due to excessive momentum.

### Run 2: Stabilized Cornering Balance
* **Parameters Changed**: `TARGET_SPEED = 120`, `STEER_GAIN = 25`, `ENABLE_TRACTION_CONTROL = True`
* **Observed/Expected Effect**: Decreasing steering gain smoothens out jerky, over-corrective steering movements. Maintaining traction control active prevents the rear wheels from spinning out during corner exits, delivering a much more stable, consistent lap despite a lower top-end speed on the main straights.

## Reflection
* **Surprising Insight**: Rule-based autonomy requires a highly delicate trade-off between speed and stability. Simply scaling up target velocity degrades overall lap efficiency because the fixed control loop cannot dynamically account for vehicle momentum changes without proactive, predictive braking.
* **Next Steps**: To scale this control logic, a predictive telemetry model like an AI-driven behavioral assistant or PID tuning wrapper could be introduced to dynamically modulate constraints based on upcoming track curvature.