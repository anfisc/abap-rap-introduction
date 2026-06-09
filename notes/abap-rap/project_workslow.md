
# General advice

Check the /DMO/FLIGHT sample implementations. E.g. in package `/DMO/FLIGHT_DRAFT` to check syntax of validations and determinations.  

# 1. create tables for the data model
# 2. Generate the RAP BO or the RAP BOs
# 3. Adapt UI
Edit generated metadata extension files
- add `@UI.hidden: true` annotation to administrative fields
- add `@UI.hidden: true` annotation to UUID based fields
- remove superflous `@UI.selectionField` annotations

# 5. Add determination(s)
- Hint: Add a determination for a field that is used as a sematic key (e.g. ContradID) in case UUID based key layout is used 
- Use Predict Business Logic for the implementation
# 4. Add validation(s)
- Use Predict Business Logic for the implementation
- Use of 
  ```%msg                = new_message_with_text(
            text   = 'Rate must not be initial'
            severity = if_abap_behv_message=>severity-error
            )
  ```   
  is fine.
  Message class is mandatory for production use but not for project work.

# 6. Add Valuehelp(s)

