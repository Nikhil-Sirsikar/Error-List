# Salesforce FIELD_CUSTOM_VALIDATION_EXCEPTION Solutions

The `FIELD_CUSTOM_VALIDATION_EXCEPTION` error in Salesforce occurs when custom validation rules on fields are violated during record creation or updates. Below are multiple criteria for the error and suggested solutions.

---

## 1. Required Field Missing
- **Criteria**: A required field is left empty, violating the validation rule.
- **Solution**: Ensure that all required fields have been filled. Review the validation rule to identify which field is being checked for a value.

    **Example**: A custom validation rule ensures that a phone number field is required. If left blank, the error occurs.

    **Fix**: Add logic in your code or update UI to ensure the field is not left empty.

---

## 2. Field Value Does Not Match Criteria
- **Criteria**: Field values must meet specific conditions (e.g., date cannot be in the past, or a number must be within a range).
- **Solution**: Verify the field's value to meet the required conditions.

    **Example**: A validation rule ensures that a "Discount" field cannot be greater than 30%. If the user enters 35%, the error occurs.

    **Fix**: Either correct the data entered or modify the rule conditions.

---

## 3. Cross-field Validation Failure
- **Criteria**: Values of two or more fields must meet certain relational criteria (e.g., "End Date" must be greater than "Start Date").
- **Solution**: Ensure that the relationship between fields satisfies the validation logic.

    **Example**: Validation rule ensures "End Date" is later than "Start Date". If "End Date" is earlier, it will throw an error.

    **Fix**: Ensure the field values follow the logical relationship.

---

## 4. Validation with Record Type or Profile
- **Criteria**: Specific validation rules are applied based on the user’s profile or the record type.
- **Solution**: Check if the user profile or record type has specific validation constraints and modify the input accordingly.

    **Example**: A validation rule enforces that for "Admin" profile, a "Special Code" field must be filled, while it's optional for others.

    **Fix**: Either provide the necessary data for specific profiles or relax the validation rule if it is too restrictive.

---

## 5. Picklist Value Validation
- **Criteria**: Picklist fields must match specific values.
- **Solution**: Ensure that the picklist value is one of the allowed values or adjust the validation rule.

    **Example**: A validation rule might restrict certain picklist options based on another field’s value.

    **Fix**: Update the field to one of the accepted values or review the logic in the validation rule.

---

## 6. Regex Validation
- **Criteria**: A field might have to match a specific format defined by a regular expression (e.g., email or phone number format).
- **Solution**: Ensure that the field value conforms to the regex format.

    **Example**: A custom validation rule checks that an email field follows the standard email format.

    **Fix**: Correct the value to fit the required format or modify the regular expression in the validation rule.

---

## 7. Field Uniqueness Constraint
- **Criteria**: A validation rule ensures that a field's value is unique across records.
- **Solution**: Check if another record already exists with the same value and either modify the new value or handle the error appropriately.

    **Example**: A rule enforces that "Account Number" must be unique across all records.

    **Fix**: Ensure that the new record doesn't duplicate existing records' unique values.

---

## Steps to Debug and Resolve the Error:
1. **Review the Validation Rule**: Go to Salesforce Setup → Object Manager → Select Object → Validation Rules to view active rules. Check for conditions that might be causing the error.
   
2. **Examine Error Messages**: Salesforce provides detailed error messages indicating which validation rule has been violated. Analyze the message to determine the cause.

3. **Test the Record**: Manually attempt saving the record and test different field inputs to identify the problematic rule.

4. **Update or Relax Rules**: If a rule is overly restrictive, modify the validation logic to allow for broader conditions or remove unnecessary constraints.

---

By following these steps and understanding the specific validation rule that triggers the error, you can resolve the `FIELD_CUSTOM_VALIDATION_EXCEPTION` efficiently.
