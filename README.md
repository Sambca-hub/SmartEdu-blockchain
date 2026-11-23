# SmartEdu

SmartEdu is a Streamlit-based smart education application. Users upload their own student dataset through the sidebar; the application no longer loads `data/students.csv`.

## Run locally or in GitHub Codespaces

```bash
pip install -r requirements.txt
streamlit run app.py
```

## Uploading a dataset

1. Open the SmartEdu website.
2. Use **Choose a student dataset** in the sidebar.
3. Upload a `.csv`, `.xlsx`, or `.xls` file.
4. Open **Dataset Upload** to preview the data.

The following columns are required (column names are case-sensitive):

- `Department`
- `Semester`
- `Subject`
- `Marks`
- `Attendance`

`Student_Name` is optional and is used for named dashboard charts.

Marks and Attendance should be numeric values from 0 to 100. Semester should contain numeric values.

## Notes

- The uploaded dataset is used by the Student Dashboard, AI Prediction, and Research Results modules.
- Learning Resources uses the uploaded dataset's Subject values when a dataset is loaded.
- The dataset is held in the Streamlit session while the app session is active. Upload it again in a new session.


## Blockchain Academic Records

The Blockchain Security page uses the currently uploaded dataset. Select a
student record and SmartEdu automatically retrieves the student's details,
marks and attendance. A grade is calculated from Marks and included in the
hashed blockchain record; users no longer need to type a grade manually.

Grade scale: A+ (90–100), A (80–89), B (70–79), C (60–69), D (50–59),
E (40–49), and F (below 40). If the dataset has no student ID column, the app
creates a display identifier based on the selected row.


## Blockchain marks editing update

The Blockchain Security page now includes an editable marks input (0–100). The grade is recalculated automatically from the entered marks. Clicking **Save Marks to Blockchain** appends a new hash-linked block, preserving earlier records rather than overwriting them. An optional correction reason is stored with each entry. Use **Verify Blockchain** to validate the complete chain.
