jQuery MultiSelect
==================

Turn a multiselect list into a nice and easy to use list with checkboxes.


## Usage
```
$('select[multiple]').multiselect();

$('select[multiple]').multiselect({
    columns: 4,
    placeholder: 'Select options'
});

$('select[multiple]').multiselect('reload');

$('select[multiple]').multiselect( 'loadOption', [{
    name   : 'Option Name 1',
    value  : 'option-value-1',
    checked: false
},{
    name   : 'Option Name 2',
    value  : 'option-value-2',
    checked: false
}]);
```
*If your list is not visible on page load, add the [jquery.actual](https://github.com/dreamerslab/jquery.actual) plugin to your project.  This will allow proper width calculations to happen.*


### Options
| Option          | Values   | Default        | Description                    |
| --------------- | -------- | -------------- | ------------------------------ |
| placeholder     | string   | Select options | default text for dropdown      |
| columns         | int      | 1              | # of columns to show options   |
| search          | bool     | false          | enable option search/filering  |
| searchOptions   | object   |                |                                |
| - default       | string   | Search         | search input placeholder text  |
| - showOptGroups | bool     | false          | show option group titles if no options remaining |
| - onSearch      | function |                | fires before search on options happens |
| selectAll       | bool     | false          | add select all option          |
| selectGroup     | bool     | false          | add select all optgroup option |
| minHeight       | number   | 200            | min height of option overlay   |
| maxHeight       | number   | null           | max height of option overlay   |
| showCheckbox    | bool     | true           | display the option checkbox    |
| onLoad          | function |                | fires at end of initial loading, hides native select list |
| onOptionClick   | function |                | fires after on option is clicked and selected |
| jqActualOpts    | object   | null           | options for [jquery.actual](https://github.com/dreamerslab/jquery.actual)      |


### Methods
**loadOptions( options, overwrite )**

Update options of select list. Default state will replace existing list with this one. *Set the second parameter to `false` to append to the list.*

*This will NOT modify the original select list element.*
```
$('select[multiple]').multiselect( 'loadOption', [{
    name   : 'Option Name 1',
    value  : 'option-value-1',
    checked: false
},{
    name   : 'Option Name 2',
    value  : 'option-value-2',
    checked: false
}]);
```


**unload**

Disable the jquery multiselect list and show the native select list.

*This is distructive. You will have to reinitialize with all options to enable the plugin for the list.*

`$('select[multiple]').multiselect( 'unload' );`


**reload**

This is a quick unload/load while maintaining options during plugin initialization.

`$('select[multiple]').multiselect( 'reload' );`


### Callbacks
**onLoad**

Fires after initial loading and hides native select list

`onLoad( element )`

element: select list element object


**onOptionClick**

*Fires after an option is clicked and selected*

`onOptionClick( element, option )`

element: select list element object

option:  option element object


**onSearch**

*Fires before search on options happens*

`searchOptions.onSearch( element )`

element: select list element object
