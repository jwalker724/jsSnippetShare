# isRequired
Form field validation class that verifies if a field is populated and if it is required and populated based on another field value (optional)

```sh
/**
* Utility function to determine if a form field is required and validate that it has a length
* @param {object} formData - keys are form field names values are form field values
* @param {string} field - the name of the field to validate
* @param optional {string} ifField - Used when a the field is only required if another field (ifField) eqs some value (ifFieldEq)
* @param optional {string} ifFieldEq - the value that the ifField would match
* @return {boolean} - true if the field is not required or contains data, and false if the field is required and is empty
* @usage - usage example for simple required name field validateRequired({name:'Sam'},'name')
* @usage - usage example for grade field if inSchool field === 'yes' validateRequired({grade:'', {inSchool:'yes'}}, 'grade', 'inSchool', 'yes')
*/
export function validateRequired(fromData, field, ifField, ifFieldEq) {
  const {fromData} = this.state;
  let verifyLength = false;
  let result = true;

  if ((ifField && fromData[ifField] === ifFieldEq) || ifField === undefined) {
    verifyLength = true;
  }
  if (verifyLength && (fromData[field] == undefined || fromData[field].trim().length < 1)) {
    result = false;
  }
  return result;
}
```
