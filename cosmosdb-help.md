### return documents containing values from an array

SELECT * FROM c WHERE 
ARRAY_CONTAINS(c.Patient.PatientIds, "888811") or 
ARRAY_CONTAINS(c.Patient.PatientIds, "888822") 
