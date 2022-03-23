# Change-language-using-google-translate
Put the JS and css code in the footer:
<div id="google_translate_element" style="display:none"></div>

<script type="text/javascript">
function googleTranslateElementInit() {
   new google.translate.TranslateElement({pageLanguage: "vi"}, 'google_translate_element');
}

function changeLanguageByButtonClick(language) {
  var selectField = document.querySelector("#google_translate_element select");
  for(var i=0; i < selectField.children.length; i++){
    var option = selectField.children[i];
    // find desired langauge and change the former language of the hidden selection-field 
    if(option.value==language){
       selectField.selectedIndex = i;
       // trigger change event afterwards to make google-lib translate this side
       selectField.dispatchEvent(new Event('change'));
       break;
    }
  }
}
</script>
<style type="text/css">
    .skiptranslate{display: none !important;}
    body{top: 0 !important;}
</style>

<script type="text/javascript" src="//translate.google.com/translate_a/element.js?cb=googleTranslateElementInit"></script>

