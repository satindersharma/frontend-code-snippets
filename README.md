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
  ```css
  .modal-header {
  cursor: move;
}
```


## Css to show Datatables scrollbar
```css
.dataTables_scrollBody::-webkit-scrollbar-track {
  box-shadow: inset 0 0 1px var(--dark-theme-top-bg-color);
  -webkit-box-shadow: inset 0 0 1px var(--dark-theme-top-bg-color);
  background-color: var(--table-thead-bg-color);
}

.dataTables_scrollBody::-webkit-scrollbar {
  width: 2rem;
  background-color: var(--table-thead-bg-color);
}

.dataTables_scrollBody::-webkit-scrollbar-thumb {
  box-shadow: inset 0 0 2px var(--dark-theme-top-bg-color);
  -webkit-box-shadow: inset 0 0 2px var(--dark-theme-top-bg-color);
  background-color: var(--dark-theme-bg-color);
}
```

### don't forget to add type="button" in the button tag if button is inside a form which have already a button with type="submit" or any button
### bottom line don't forget to add type of button inside forms


## If your are getting this error in selecet2
## Uncaught Error: No select2/compat/inputData
this means you are assign ing select2 on input but it require a select tag




# How to write javascript direclty into firefox or
# run or edit javascript in browser

###### (go to your browser console (ctrl + shift + i or f12) and go to console tab) or ctrl + shift + k
######  (click on swith to multi-line editor mode) or (ctrl + b  note:-if you are not in web developer toolbar this will trigger bookmarks)
######  wrap you function inside

```javascript
(function() {
})();
```
`note: ` remove 
```javascript
window.addEventListener("load", () => {});
```

###### add off() to your events(jquery events) as they will attach agian and agian when you run the script
###### (to run script click on run) or (ctrl + enter)

###### example

```javascript
// (go to your browser console (ctrl + shift + i or f12) and go to console tab) or ctrl + shift + k
// (click on swith to multi-line editor mode) or (ctrl + b  note:-if you are not in web developer toolbar this will trigger bookmarks)
// wrap you function inside
/* ----
(function() {
})();
note: remove window.addEventListener("load", () => {});

--- */
// add off() toyour events(jquery events) as they will attach agian and agian when you run the script
// (to run script click on run) or (ctrl + enter)


// eg.



(function () {
  //

  let bom_form = $("#add-bom-form");
  bom_form.submit(function (e) {
    // e.preventDefault();
    $(".item-formset-div").first().remove();
    return true;
  });

  // let bom_form = $("#add-bom-form");
  // bom_form.submit(function (e) {
  //   e.preventDefault();
  //   $(".item-formset-div").first().remove();
  //   let serializedData = new FormData(this);
  //   console.log(window.snapshot_array);
  //   let item_name = serializedData.get("bom-name");
  //   $.each(window.snapshot_array, function (k, v) {
  //     let file = v[0];
  //     let filename = item_name + v[1];
  //     console.table(file, filename);
  //     serializedData.append("bom-image", file, filename);
  //   });
  //   console.log(serializedData.getAll("bom-image"));
  //   $.ajax({
  //     type: bom_form.attr("method"),
  //     url: bom_form.attr("action"),
  //     data: serializedData,
  //     cache: false,
  //     contentType: false,
  //     processData: false,
  //     success: function (data) {
  //       $.confirm({
  //         title: "Success!",
  //         content: data.content,
  //         theme: "modern",
  //         autoClose: "ok|1000",
  //         escapeKey: true,
  //         draggable: true,
  //         onClose: function () {
  //           bom_form_reset();
  //           $("#bom-add-modal").modal("hide");
  //           return true;
  //         },
  //         backgroundDismiss: function () {
  //           bom_form_reset();
  //           $("#bom-add-modal").modal("hide");
  //           return true;
  //         },
  //         buttons: {
  //           ok: function () {
  //             bom_form_reset();
  //             $("#bom-add-modal").modal("hide");
  //           },
  //         },
  //       });
  //     },
  //   });
  // });
  

  /* ---- Add button function ---*/
  // $(".add-remove .add-bom-item-btn").on('click',function(e){
  //   e.preventDefault()
  //   let self = $(this)
  //   console.log(self.closest('.add-remove'))
  // })

  function changeNewCopy(newCopy, formset_div, item_val, clickCoutner) {
    let self = $(newCopy);
    let cloneDiv = self.closest(formset_div).clone();
    $(cloneDiv).find("#id_bom-item-0-item").val(item_val).trigger("change");

    cloneDiv
      .find('label[for="id_bom-item-0-item"]')
      .attr("for", `id_bom-item-${clickCoutner}-item`);
    cloneDiv.find("#id_bom-item-0-item").attr({
      id: `id_bom-item-${clickCoutner}-item`,
      name: `bom-item-${clickCoutner}-item`,
      required: true,
    });
    cloneDiv
      .find('label[for="id_bom-item-0-item_reference"]')
      .attr("for", `id_bom-item-${clickCoutner}-item_reference`);
    cloneDiv.find("#id_bom-item-0-item_reference").attr({
      id: `id_bom-item-${clickCoutner}-item_reference`,
      name: `bom-item-${clickCoutner}-item_reference`,
      required: true,
    });
    // change text add to remove
    let btnDiv = $(cloneDiv).find(".add-bom-item-btn").closest(".form-group");
    $(btnDiv)
      .find(".add-bom-item-btn-text")
      .removeClass("add-bom-item-btn-text")
      .addClass("remove-bom-item-btn-text")
      .text("Remove");
    // change icon add remove
    let removeBtn = $(btnDiv)
      .find(".add-bom-item-btn")
      .removeClass("add-bom-item-btn ri-add-circle-line")
      .addClass("remove-bom-item-btn ri-close-circle-line");

    $(removeBtn).off().on("click", function () {
      $(this).closest(".item-formset-div").remove();

      // $(".item-formset-div").each(function (k, v) {});
      // decrease total form no by one (as div not upaded here thus minus 1)
      $("#id_bom-item-TOTAL_FORMS").val($(".item-formset-div").length - 1);
    });
    // increase when a new added
    $("#id_bom-item-TOTAL_FORMS").val($(".item-formset-div").length);
    return cloneDiv;
  }
  var clickCoutner = 0;
  $(".add-bom-item-btn").off().on("click", function (e) {
    e.preventDefault();
    let formset_div = ".item-formset-div";
    let item_val = $(formset_div)
      .first()
      .find("#id_bom-item-0-item option:selected")
      .val();
    let item_reference = $(formset_div)
      .first()
      .find("#id_bom-item-0-item_reference")
      .val();
    if (item_val && item_reference) {
      clickCoutner += 1;
      console.log(item_val);
      let self = $(this);
      let formset_div = ".item-formset-div";
      let new_copy = changeNewCopy(self, formset_div, item_val, clickCoutner);

      $(formset_div).first().find("#id_bom-item-0-item_reference").val("");
      // new_copy = new_copy.remove(self.closest('.form-group'))
      // let fdiv =
      $(formset_div).first().next().after(new_copy);
    } else {
      // console.log('error')
      $.alert({
        title: "Alert!",
        content: "Both Fields are Required",
        // icon: "ri-error-warning-fill text-dark",
        theme: "modern",
        autoClose: "ok|1000",
        escapseKey: true,
        draggable: true,
        onClose: function () {
          return true;
        },
        backgroundDismiss: function () {
          return true;
        },
        buttons: {
          ok: function () {
            return true;
          },
        },
      });
    }
  });
  // $(`<div class="line-divider-darker"></div>`).insertAfter(
  //   $(".item-formset-div").first()
  // );
  // $("#id_bom-item-0-item").attr('required',true)
  // $("#id_bom-item-0-item_reference").attr('required',true)
})();
```





# Custom form control bootsrap


if you are adding col-form-label it will add extra top padding so to make checkbox input and label align add pt-0 to the label
format should be 


`.form-row>.form-group.col-md-4>.col-sm-6.ml-3.custom-control.custom-checkbox>input:checkbox.custom-control-input+label.col-form-label.pt-0.custom-control-label^.col-sm-12>input`

```html
 <div class="form-row">
     <div class="form-group col-md-4">
         <div class="col-sm-6 ml-3 my-auto custom-control custom-checkbox">
             <input type="checkbox" name="" id="id_is_serial_checkbox" class="custom-control-input">
             <label for="id_is_serial_checkbox" class="col-form-label pt-0 custom-control-label">Is Serial</label></div>
         <div class="col-sm-12"><input id="id_is_serial" class="form-control" type="text"></div>
     </div>
 </div>
```
