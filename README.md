# FluentFormsWordpress
PHP snippet to add additional Validation for a specific form field 

## Validation
### Example

this code will check a specific field (volgorde_field) on a specific form (form_id 10).
here is will see if the input is between 1 and 60. Otherwise it will send a error message.
```
add_filter('fluentform_validate_input_item_input_text', function ($errorMessage, $field, $formData, $fields, $form) {
	$fieldName = 'volgorde_field';
	$target_form_id  = 10;
	$inputValue = $formData[$fieldName];
	$int_inputValue = intval($inputValue);
	
	if($form->id != $target_form_id) { 
		return $errorMessage; 
	}
   	else {
		if ($field['name'] == 'volgorde_field')  {
			if ($int_inputValue < 1 || $int_inputValue > 60 ) {
				$errorMessage = 'Kies een positie tussen de 1 en 60';
				return [$errorMessage];
			}
			else if {
				
			}
			else {
				return $errorMessage;
			}
		}
	}
}, 10, 5);
```
