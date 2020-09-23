# frontend-code-snippets


# working with dropdown in js

#### empty a dropdown

```javascript
$("#id_pincode").empty();
```

##### filter a array

```javascript
let result = newdata.filter( ({ taluk }) =>taluk === e.params.data.id);
```

##### Make a unique dropdown

######  short a set

###### this will conver a set into array and then sort it

 [...uniquepin].sort()
###### how to add new option to dropdown

```javascript
 var newOption = new Option(k, k, false, false);
           $("#id_pincode").append(newOption).trigger("change");
```

```javascript
    [...uniquepin].sort().forEach(function (k, v) {
      if (k !== undefined) {
        // pincode_result.innerHTML += `<option class="dropdown-item pitems" value="${k}">${k}</option>`;
            var newOption = new Option(k, k, false, false);
           $("#id_pincode").append(newOption).trigger("change");
      }
    });
```


