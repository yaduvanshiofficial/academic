<?php
$toEmail = "yaduvanshiankit@outlook.com";
$name = strip_tags(trim($_POST["userName"]));
$name = str_replace(array("\r","\n"),array(" "," "),$name);
$fromEmail = filter_var(trim($_POST["userEmail"]), FILTER_SANITIZE_EMAIL);
$subject = trim($_POST["subject"]);
$content = trim($_POST["content"]);

$mailHeaders = "From: " . $name . "<". $fromEmail .">\r\n";
if(mail($toEmail, $subject, $content, $mailHeaders)) {
    print "<p class='success' style='background-color: #0DADB7;'>Thank You! Your message has been sent.</p>";
} else {
    print "<p class='error' style='background-color: #e60000;'>Oops! Something went wrong and we couldn't send your message.</p>";
}
?>
