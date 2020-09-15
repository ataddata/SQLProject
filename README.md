# SQLProject

# Identifying patients with certain diagnosis codes using regex

SELECT COUNT(DISTINCT diagnosis.patient_guid) FROM diagnosis
LEFT JOIN history
ON diagnosis.patient_diagnosis_id = history.patient_diagnosis_id
WHERE (diagnosis.dx_code REGEXP '361\.0[0-7]|(?i)H33\.0[0-5][1-3,9]|(?i)H33\.8')
AND (DATE(history.dx_date) BETWEEN '2013-01-01' AND '2018-12-31');
