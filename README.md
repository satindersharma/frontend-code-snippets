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

```javascript
 [...uniquepin].sort()
```
 
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

##### empty drop down and set a value

```javascript
$("#id_pincode").val(null).trigger("change");
 $("#id_pincode").val(result[0].pincode).trigger("change");
```

### timezoe of user
```javascript
# console.log(Intl.DateTimeFormat().resolvedOptions().timeZone)
```


### change the url and reload to that url
```javascript
window.location.href = "/lead/";
```

### change the url but not reload
```javascript
window.history.pushState("", "", "/lead/");
```



### get options text and value
```javascript
date_filter_id.addEventListener("change",(e)=>{
 var tragettext = e.target.options[e.target.selectedIndex].text;
 var evalue = e.target.value;
 console.log(tragettext)
  console.log(evalue)
 });
 ```
 
 
 
 ### make modal header draggable
 ```javascript
   $("#modal-id-for-followup").draggable({
    handle: ".modal-header",
  });
  ```
