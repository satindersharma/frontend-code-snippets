  $(".select2-results__options).is(":hover")
  is not working so convert it to 
  $(".select2-results__options:hover").length
  
  
  
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
