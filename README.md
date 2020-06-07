# Gmail-FormSubmit-EmailReply
Creation of automatic response to Gmail FormSubmit with customized email

function onFormSubmit(e) {
  var values = e.namedValues;
  Logger.log(values);
  var htmlBody = '<ul>';
  for (Key in values) {
    var label = Key;
    var data = values[Key];
    htmlBody += '<li>' + label + ": " + data + '</li>';
  };
  htmlBody += '</ul>';
  GmailApp.sendEmail('gm.hieroanoke@gmail.com', 'New Sales Lead', '{htmlBody:htmlBody}');
  
}
