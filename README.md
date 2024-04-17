#J.F Script for autmatic google messages based on an email input from a sheet :)

function sendemail(e) {
  var namedValues = e.namedValues;
  var recipient = namedValues["Email Address"];
  var FName = namedValues["First Name"];
  var LName = namedValues["Last Name"];

  var subject = "Greetings " + FName + " " + LName + " - ";

  var file = DriveApp.getFileById('file id');
  var fileBlob = file.getBlob();

  var options = {
    htmlBody: `Greetings ${FName}, ${LName} ,


words go here

 attachments:[fileBlob] };

  GmailApp.sendEmail(recipient, subject, "", options);
  }
