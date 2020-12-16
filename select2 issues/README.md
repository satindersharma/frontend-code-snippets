  ```javascript
  $(".select2-results__options).is(":hover")
  ```
  ### is not working so convert it to 
  ```javascript
  $(".select2-results__options:hover").length
  ```
  
  
  ```javascript
  
  $(".modal").on("wheel", function () {
    // console.log($(".select2").hasClass("select2-container--below select2-container--open"))
    if (
      $("#id_city").is(":empty") ||
      !$(".select2-results__options:hover").length ||
      ($(".select2-search__field").is(":focus") &&
        !$(".select2-results__options:hover").length)
    ) {
      console.log("clossing select2 due to wheel");
      $("#id_city").select2("close");
      // $('#id_city').select2('destroy');
      // $('#id_city').off('select2:select');
      // $(".select2-search__field").focusout();
    }
  });


  ```






```javascript



$("#id-lead-filter-form").find("#id_statename_filter").val(null).trigger('change');


    language: {
      noResults: function () {
        return "Search for district";
      },
    },
    escapeMarkup: function (markup) {
      return markup;
    },
    
    
        language: {
      errorLoading: function () {
        return "Search for city";
      },
    },
    
    
    
    
       width: "resolve",
    // theme: "classic",
    // allowClear: true,
    theme: "bootstrap",
    
    
   ```

### The working wheel on select2

```javascript
  $(".modal").on("wheel", function () {
    if (
      $(".select2-search__field").length !== 0 ||
      $(".select2-results__options").length !== 0
    ) {
      // if (
      //   !$(".select2-search__field").val().length ||
      //   !$(".select2-search__field").is(":focus") ||
      //   (!$(".select2-search__field").is(":hover") &&
      //     !$(".select2-results__options").is(":hover") &&
      //     !$(".select2-selection").is(":hover") &&
      //     !$(".select2-dropdown").is(":hover"))
      // )
      if (
        !$(".select2-search__field").is(":focus") ||
        (!$(".select2-search__field:hover").length &&
          !$(".select2-results__options:hover").length &&
          !$(".select2-selection:hover").length &&
          !$(".select2-dropdown:hover").length)
      ) {
        console.log("clossing select2 due to wheel");
        $(
          "#id_city, #id_state , #id_district , #id_dealer_transfer , #id_dealer , #id_lead_source , #id_lead_status , #id_lead_source_type , #id_followup_score , #id_followup_status , #id_deal_type , #id_transfer , #id_product_category , #id_product , #id_exe_share , #id_sub_dealer_share , #id_rse_share , #id_customer_share , #id_other_share , #id_sub_dealer , #id_rse"
        ).select2("close");
      }
    }
  });
  ```


### select2.min.js:1 Uncaught Error: No select2/compat/inputData


change `<input >` to `<select>`
  
via widget in django form

`widget=forms.TextInput    `          to

`widget=forms.Select`



### select2 won't appear on top

add dropdownParent

#### inside jquery confirm

```javascript
$.dialog{
....
onContentReady: function () {

let self = this;
// console.log("to see all",self)
// check if it is inside a modal
if (self.$el.parents(".modal-open:first").length !== 0) {
  console.log("inside the modal");
  // thes were the fixes the i don't require
  // $.fn.modal.Constructor.prototype._enforceFocus = function () {};
  // $.fn.modal.Constructor.prototype.enforceFocus = function () {};

 // increase z-index if unable to search on select2 input
  self.$el
    .find(".select2-container, .select2-drop, .select2-drop-mask")
    .css("z-index", 999999);
}
        
// set dropdown parent if you are uing select2 inside the dialog 
let dropdownParent = self.$el;
popupCity.select2({
            tags: true,
            placeholder: "Select City",
            width: "resolve",
            allowClear: true,
            theme: "bootstrap",
            dropdownParent: dropdownParent,
            });
// find content on jquery confirm
let popupDistrict = self.$content.find('[name="popup-district"]');

// to close the dialog
self.$closeIcon.trigger("click");
}
```

### select2  appear on top but unable to type on input / unable to focus on input

removing the attribute `tabindex="-1"` from the element.

