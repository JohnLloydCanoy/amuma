# Data Analytic


## Dimension check: 
the raw data contains 709 rows and 31 columns <br>
![Dimension](documentation/dimension.png)  


## Data before cleaning 

**Data Overview:**
- **Class:** pandas.DataFrame
- **RangeIndex:** 709 entries, 0 to 708
- **Data columns:** 31 columns total
- **Memory usage:** 171.8 KB
- **Data Types:** float64 (2), int64 (5), str (24)

| # | Column | Non-Null Count | Dtype |
|---|--------|----------------|-------|
| 0 | Informed Consent | 709 non-null | str |
| 1 | School ( Please. Dont Abbreviate) | 707 non-null | str |
| 2 | College/Department ( Please. Dont Abbreviate) | 671 non-null | str |
| 3 | Program (Please. Dont Abbreviate) | 662 non-null | str |
| 4 | Age | 672 non-null | float64 |
| 5 | Current Year Level | 688 non-null | str |
| 6 | What language or dialect are you most comfortable using when expressing complex emotions or mental health struggles? | 702 non-null | str |
| 7 | Academic Stress (e.g., heavy workload, difficulty of subjects, upcoming exams, deadlines) [Choose] | 709 non-null | str |
| 8 | Personal / Intrapersonal Stress (e.g., changes in sleeping or eating habits, personal health, taking on new responsibilities) [Choose] | 709 non-null | str |
| 9 | Interpersonal / Social Stress (e.g., peer relationships, romantic issues, conflicts with friends or family) [Choose] | 709 non-null | str |
| 10 | Environmental / Financial Stress (e.g., budgeting expenses, paying for tuition, living conditions, finding a quiet place to study) [Choose] | 709 non-null | str |
| 11 | When you are experiencing high levels of stress, what type of support do you typically look for FIRST? | 709 non-null | str |
| 12 | When experiencing emotional distress, who or where do you typically go to FIRST for advice or comfort? | 709 non-null | str |
| 13 | Have you ever attempted to schedule an appointment or speak with a campus guidance counselor or mental health professional? | 709 non-null | str |
| 14 | If you answered YES, how would you rate your comfort level with the manual process of booking that face-to-face appointment? (1 = Very Hesitant, 5 = Very Comfortable) | 160 non-null | float64 |
| 15 | If you answered YES, what happened after your initial consultation or counseling session? (Multiple choice) | 123 non-null | str |
| 16 | If you answered NO, what is the primary reason you have avoided seeking help from a campus guidance counselor? (Multiple Select) | 646 non-null | str |
| 17 | What time of day do you most frequently feel overwhelmed and in need of emotional support? (Multiple choice). | 709 non-null | str |
| 18 | Which of the following Amuma AI features would make you most likely to use the platform when stressed? (Checkbox, multi-select) | 704 non-null | str |
| 19 | Amuma AI is designed for mobile use. Which of the following technical or environmental limitations would prevent you from using a voice-based mental health app? (Checkbox, multi-select) | 709 non-null | str |
| 20 | Amuma AI allows you to vent via a conversational voice call with the AI rather than typing. How comfortable would you be speaking your struggles out loud to an empathetic AI? (Multiple choice) | 709 non-null | str |
| 21 | When considering using an AI for mental health support, what is your primary concern or reason for distrust? (Checkbox, multi-select) | 705 non-null | str |
| 22 | To encourage daily mental wellness, Amuma AI includes gamified features. Which of these would motivate you most to open the app every day? (Checkbox, multi-select) | 703 non-null | str |
| 23 | Rank the following factors by priority when using a digital mental health platform. (1 = Most Important, 5 = Least Important) [Strict data privacy and anonymity] | 709 non-null | int64 |
| 24 | Rank the following factors by priority when using a digital mental health platform. (1 = Most Important, 5 = Least Important) [A natural, empathetic, and non-robotic AI tone] | 709 non-null | int64 |
| 25 | Rank the following factors by priority when using a digital mental health platform. (1 = Most Important, 5 = Least Important) [A frictionless, easy way to book a human professional if needed] | 709 non-null | int64 |
| 26 | Rank the following factors by priority when using a digital mental health platform. (1 = Most Important, 5 = Least Important) [The ability to communicate via voice/audio instead of typing] | 709 non-null | int64 |
| 27 | Rank the following factors by priority when using a digital mental health platform. (1 = Most Important, 5 = Least Important) [Gamified post-counseling support and daily wellness tracking (e.g., virtual pets and streaks)] | 709 non-null | int64 |
| 28 | For the "Emergency Fast-Tracking" feature to work during a severe crisis, the system may need to securely bridge your anonymous profile to campus or city health services. Under what condition would you accept this? (Multiple choice) | 703 non-null | str |
| 29 | Suggestions: Do you have any other suggestions, privacy concerns, or specific features you would want to see in a university mental health application? (Open-ended, optional) | 87 non-null | str |
| 30 | Required to take part. Tick each box: | 709 non-null | str |

