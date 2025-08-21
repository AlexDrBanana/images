## Binary Logit 1

![Binary Logit 1](https://cdn.jsdelivr.net/gh/AlexDrBanana/images@main/uPic/3nlSSP.png)

**Pregnancies**: Number of times the patient has been pregnant.
**Glucose**: 2-hour plasma glucose concentration in an oral glucose tolerance test (mg/dL). Zeros often indicate missing.
**BloodPressure**: Diastolic blood pressure (mm Hg). Zeros may be missing.
**SkinThickness**: Triceps skinfold thickness (mm). Zeros commonly stand for missing.
**Insulin**: 2-hour serum insulin (µU/mL). Many zeros = likely missing.
**BMI**: Body Mass Index = weight (kg) / height (m)^2. Zero implies missing or bad entry.
**DiabetesPedigreeFunction**: A calculated score summarizing genetic/hereditary likelihood of diabetes based on family history.
**Age**: Age in years.
**Outcome**: Target variable; 1 = diabetes diagnosed, 0 = no diabetes.

## Binary Logit 2

![Binary Logit 2](https://cdn.jsdelivr.net/gh/AlexDrBanana/images@main/uPic/KdBpTi.png)

**choice_1**: Dependent variable; 1 if alternative (car) 1 was chosen by the respondent, 0 otherwise.
**seat_1**: Seat comfort / quality score (e.g., rating for seats of car 1). Positive coefficient: higher comfort increases utility.
**seat_1_sq**: Squared seat comfort term capturing diminishing (concave) marginal utility (negative coefficient indicates diminishing returns after higher comfort levels).
**price_1**: Purchase (or lease) price of car 1 (in given currency units). Negative coefficient: higher price lowers utility.
**trans_1_auto**: Indicator (1 = automatic transmission, 0 = otherwise). Positive coefficient: automatic transmission preferred.
**convert_1_yes**: Indicator (1 = convertible, 0 = non‑convertible). Small, non‑significant positive coefficient suggests weak or ambiguous preference within sampled data.

## MNLogit 1

![MNLogit 1](https://cdn.jsdelivr.net/gh/AlexDrBanana/images@main/uPic/MNPWsa.png)

**mode (alt)**: The fishing mode selected for the trip. This is a categorical variable with four possible values:
  1. Beach
  2. Pier
  3. Private boat
  4. Charter boat

**price_x**: The cost of each fishing mode (in dollars). For example, `price_beach` is the cost of fishing from the beach for one trip.
**catch_x**: The catch rate for each fishing mode (in catches per hour). For example, `catch_beach` is the catch rate for the beach alternative.
**income**: The monthly income of the recreational fisher (in dollars).
**id**: A unique identifier for each individual in the dataset.
**choice**: Indicates whether the individual chose the given alternative (used in long-format datasets).

## MNLogit 2

![MNLogit 2](https://cdn.jsdelivr.net/gh/AlexDrBanana/images@main/uPic/pmc28E.png)

**CHOICE**: The selected travel alternative for an observed trip. Encoded as categorical outcomes (0=unknown, 1=train, 2=Swissmetro, 3=car). The multinomial model estimates utility differences across these alternatives relative to an internal baseline (reference category not explicitly shown in the printed table).

**TRAIN_TT** (Train Travel Time): In-vehicle travel time for the conventional train alternative (typically in minutes). Higher time is expected to reduce the utility of choosing train (negative effect). A positive coefficient here (as in your output) may reflect scaling issues, multicollinearity, or that times are similar and picking up noise—worth re-checking units or adding cost variables.

**SM_TT** (Swissmetro Travel Time): Hypothetical high-speed (Swissmetro) in-vehicle travel time. Lower time should raise the Swissmetro utility; thus you expect a negative coefficient (since more time lowers utility). Negative significant coefficients match behavioral expectations.

**CAR_TT** (Car Travel Time): Travel time for the car alternative. Longer car time should lower the probability of choosing car relative to the reference. Small (sometimes insignificant) negative coefficients suggest limited variation or overlap with other variables.

**AGE**: Age of the respondent (years). Often included to capture heterogeneity in mode preferences (e.g., older passengers may value comfort or reliability differently). Frequently not strongly significant unless preferences vary sharply across age groups. Insignificance here suggests age does not explain much incremental variation beyond the level-of-service attributes.

**INCOME**: Respondent income (often monthly or annual; check dataset documentation for units). Intended to capture differences in cost sensitivity (higher-income travellers may be less price sensitive, indirectly affecting relative time valuation). Near-zero, insignificant coefficients indicate no clear direct linear effect in this reduced specification (price variables might be missing here; without explicit costs income has little to act through).